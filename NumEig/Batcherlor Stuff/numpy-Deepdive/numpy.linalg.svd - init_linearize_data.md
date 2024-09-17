[[numpy.linalg.SVD]] #NumEig
assighning rows and strides?
```static inline void
init_linearize_data(LINEARIZE_DATA_t *lin_data,
                    npy_intp rows,
                    npy_intp columns,
                    npy_intp row_strides,
                    npy_intp column_strides)
{
    init_linearize_data_ex(
        lin_data, rows, columns, row_strides, column_strides, columns);
}
```