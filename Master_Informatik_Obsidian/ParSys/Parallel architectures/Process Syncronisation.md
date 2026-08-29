- exchange control information
- non-interruptable sequences: read, write, read-modify-write

###  Test&Set(lock)
```
Test & Set ( lock )
	tmp := lock ;
	lock := 1;
	return ( tmp )
```
### Reset(lock):
```
Reset ( lock )
	lock := 0
```
- repeat Test&Set until return lock = 0

# Interceptor
if lock = 1: all interrupts are disabled
when lock = 0 signal all waiting processors with interrupt