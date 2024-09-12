[[numpy.linalg.SVD]] NumEigNumerischeEigenwerte 
performed on parameters
call LAPACK's Singular Value Decomposition (SVD)

```
call_gesdd(GESDD_PARAMS_t<fortran_real> *params)
{
    fortran_int rv;
    LAPACK(sgesdd)(&params->JOBZ, &params->M, &params->N,
                          params->A, &params->LDA,
                          params->S,
                          params->U, &params->LDU,
                          params->VT, &params->LDVT,
                          params->WORK, &params->LWORK,
                          (fortran_int*)params->IWORK,
                          &rv);
    return rv;
}
static inline fortran_int
call_gesdd(GESDD_PARAMS_t<fortran_doublereal> *params)
{
    fortran_int rv;
    LAPACK(dgesdd)(&params->JOBZ, &params->M, &params->N,
                          params->A, &params->LDA,
                          params->S,
                          params->U, &params->LDU,
                          params->VT, &params->LDVT,
                          params->WORK, &params->LWORK,
                          (fortran_int*)params->IWORK,
                          &rv);
    return rv;
}
```

Process:
1. call LAPACK Routine taylored to input matrix
	1. sgesdd for single precision real numbers and dgesdd for doubble precision real numbers
2. Pass parameters into a LAPACK structure
3. set returnvalues
In this way, SVD without complicated structural stuff, but just GESDD_Params_t structure.