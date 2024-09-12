[[numpy.linalg.SVD]] NumEigNumerischeEigenwerte 
```
template<typename typ>
static inline void *
delinearize_matrix(typ *dst,
                          typ *src,
                          const LINEARIZE_DATA_t* data)
{
```
$*$dst = destination pointer
$*$src = source, where info comes from
data = methadata on shapes and strides of origional matrix
```
using ftyp = fortran_type_t<typ>;

    if (src) {
        int i;
        typ *rv = src;
        fortran_int columns = (fortran_int)data->columns;
        fortran_int column_strides =
            (fortran_int)(data->column_strides/sizeof(typ));
        fortran_int one = 1;
        for (i = 0; i < data->rows; i++) {
            if (column_strides > 0) {
                copy(&columns,
                              (ftyp*)src, &one,
                              (ftyp*)dst, &column_strides);
            }
            else if (column_strides < 0) {
                copy(&columns,
                              (ftyp*)src, &one,
                              ((ftyp*)dst + (columns-1)*column_strides),
                              &column_strides);
            }
            else {
                /*
                 * Zero stride has undefined behavior in some BLAS
                 * implementations (e.g. OSX Accelerate), so do it
                 * manually
                 */
                if (columns > 0) {
                    memcpy(dst,
                           src + (columns-1),
                           sizeof(typ));
                }
            }
            src += data->output_lead_dim;
            dst += data->row_strides/sizeof(typ);
        }

        return rv;
    } else {
        return src;
    }
}

```

What dose strides mean? what info is saved in that?
That is For large matrisies how they are grouped to do svd on these sections individually