We can not directly define OU global variables as C++ global variables, as C++ will try to initialize them before executing the main function.
However, if the global variable has array in it, then the program will crash. This is because initializing an array will trigger EMP to invoke some zk computation, which can only be executed after establishing connection between two parties.
To solve this problem, we define those global variables as pointers, and allocate the real data after connection is established.