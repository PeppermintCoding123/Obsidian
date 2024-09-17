Github sourcs code on SVD:
https://github.com/numpy/numpy/blob/main/numpy/linalg/umath_linalg.cpp
[[Question - Why Krylov SVD better than normal SVD]]
#NumEig
#### general overviev:
- in c++

```
template<typename typ>
static inline void
svd_wrapper(char JOBZ,
                   char **args,
                   npy_intp const *dimensions,
                   npy_intp const *steps)
{
```
Initalizing wrapper 
#### Parameters
- job flags (`JOBZ`) - type of result with just U or V or none or both
- pointers to arguments (`args`) - result storage
- dimensions of the matrices involved (`dimensions`) - input dimension pointer
- steps for memory allocation (`steps`) - size of blocks for large matrices


```
using basetyp = basetype_t<typ>;
    ptrdiff_t outer_steps[4];
    int error_occurred = get_fp_invalid_and_clear();
    size_t iter;
    size_t outer_dim = *dimensions++;
    size_t op_count = (JOBZ=='N')?2:4;
```
Setting parameters for types and flagpointers

```
    GESDD_PARAMS_t<typ> params;

    for (iter = 0; iter < op_count; ++iter) {
        outer_steps[iter] = (ptrdiff_t) steps[iter];
    }
    steps += op_count;
```
Initialize structure

```
	if (init_gesdd(&params,
                   JOBZ,
                   (fortran_int)dimensions[0],
                   (fortran_int)dimensions[1],
dispatch_scalar<typ>())) {
        LINEARIZE_DATA_t a_in, u_out = {}, s_out = {}, v_out = {};
        fortran_int min_m_n = params.M < params.N ? params.M : params.N;
```
Find out what parameterzize is like
```
init_linearize_data(&a_in, params.N, params.M, steps[1], steps[0]);
        if ('N' == params.JOBZ) {
            /* only the singular values are wanted */
            init_linearize_data(&s_out, 1, min_m_n, 0, steps[2]);
        } else {
            fortran_int u_columns, v_rows;
            if ('S' == params.JOBZ) {
                u_columns = min_m_n;
                v_rows = min_m_n;
            } else { /* JOBZ == 'A' */
                u_columns = params.M;
                v_rows = params.N;
            }
            init_linearize_data(&u_out,
                                u_columns, params.M,
                                steps[3], steps[2]);
            init_linearize_data(&s_out,
                                1, min_m_n,
                                0, steps[4]);
            init_linearize_data(&v_out,
                                params.N, v_rows,
                                steps[6], steps[5]);
        }
```
Devide up according to correct columb and row amount and applying [[numpy.linalg.svd - init_linearize_data]]
```
        for (iter = 0; iter < outer_dim; ++iter) {
            int not_ok;
            /* copy the matrix in */
            linearize_matrix((typ*)params.A, (typ*)args[0], &a_in);
            not_ok = call_gesdd(&params);
            if (!not_ok) {
                if ('N' == params.JOBZ) {
                    delinearize_matrix((basetyp*)args[1], (basetyp*)params.S, &s_out);
                } else {
                    if ('A' == params.JOBZ && min_m_n == 0) {
                        /* Lapack has betrayed us and left these uninitialized,
                         * so produce an identity matrix for whichever of u
                         * and v is not empty.
                         */
                        identity_matrix((typ*)params.U, params.M);
                        identity_matrix((typ*)params.VT, params.N);
                    }

                    delinearize_matrix((typ*)args[1], (typ*)params.U, &u_out);
                    delinearize_matrix((basetyp*)args[2], (basetyp*)params.S, &s_out);
                    delinearize_matrix((typ*)args[3], (typ*)params.VT, &v_out);
                }
```
[[call_gesdd]] (assighn parameters to corrcet variables) decides if the parameters 
will work. 
if(not_ok) then throw error and return NAN.
if(ok) then [[numpy.linalg.svd - delinearize_matrix]]


```
            } else {
                error_occurred = 1;
                if ('N' == params.JOBZ) {
                    nan_matrix((basetyp*)args[1], &s_out);
                } else {
                    nan_matrix((typ*)args[1], &u_out);
                    nan_matrix((basetyp*)args[2], &s_out);
                    nan_matrix((typ*)args[3], &v_out);
                }
            }
            update_pointers((npy_uint8**)args, outer_steps, op_count);
        }
        release_gesdd(&params);
    }
```
Sets the floating-point invalid flag if an error occurred.
    
```
set_fp_invalid_or_clear(error_occurred);
}
```
clear all inputs of results
```

template<typename typ>
static void
svd_N(char **args,
             npy_intp const *dimensions,
             npy_intp const *steps,
             void *NPY_UNUSED(func))
{
    svd_wrapper<fortran_type_t<typ>>('N', args, dimensions, steps);
}

template<typename typ>
static void
svd_S(char **args,
             npy_intp const *dimensions,
             npy_intp const *steps,
             void *NPY_UNUSED(func))
{
    svd_wrapper<fortran_type_t<typ>>('S', args, dimensions, steps);
}

template<typename typ>
static void
svd_A(char **args,
             npy_intp const *dimensions,
             npy_intp const *steps,
             void *NPY_UNUSED(func))
{
    svd_wrapper<fortran_type_t<typ>>('A', args, dimensions, steps);
}

```
Apply svd_wrapper with diffarent settings