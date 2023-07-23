Dependencies:

COIN: sudo apt install coinor-libipopt-dev

CPPAD: sudo apt-get install cppad

IPOPT: https://coin-or.github.io/Ipopt/INSTALL.html

test_case: https://www.coin-or.org/CppAD/Doc/ipopt_solve_get_started.cpp.htm

Note: if you have such error: "#  error "don't have header file for stddef" when compiling, 
try to modify the header file:/usr/include/coin/IpSmartPtr.hpp as followings:

    #define HAVE_CSTDDEF // new line    
    #ifdef HAVE_CSTDDEF    
    # include <cstddef>    
    #else    
    # ifdef HAVE_STDDEF_H    
    #  include <stddef.h>    
    # else    
    #  error "don't have header file for stddef"    
    # endif    
    #endif    
    #undef HAVE_CSTDDEF // new line    
