# Introduction #

**gmpy** is a Python module that provides access to the GNU Multiple Precision (GMP) libary. GMP provides very fast and highly optimised routines for working with arbitrary precision integers (MPZ), rationals (MPQ), and floating point numbers (MPF). The GMP types are exposed to Python as **gmpy.mpz**, **gmpy.mpq**, and **gmpy.mpf**.

**gmpy** supports both Python 2 and 3.  Due to differences between Python 2 and 3, a small number of behavioral changes were introduced in version 1.10 and later relative to previous releases (version 1.04 and earlier). To allow more extensive changes without silently breaking applications, the development version has been renamed to **gmpy2**. **gmpy2** is in beta status and the API should be stable (i.e. no more backwards incompatible changes). To import **gmpy2**, you must use `import gmpy2`.

# Enhancements in gmpy2 #

  * Floating point support is provided by the MPFR library instead of using the MPF type from GMP. MPFR provides correctly rounded floating point arithmetic and a wide variety of transcendental functions. MPFR is exposed to Python as **gmpy2.mpfr**. The old **mpf** type no longer exists in **gmpy2**. Partial support was introduced in Alpha1. Improved support (context manager, subnormals, etc.) will be included in Alpha2.
  * Arbitrary precision complex numbers are provided by the MPC library.
  * A mutable integer type is available as **gmpy2.xmpz**. In addition to slightly faster performance for in-place operations, the **xmpz** allows slices to be used for setting and clearing individual bits.
  * A large number of minor changes were made:
    * Wrapped rootrem, fib2, lucas, and lucas2.
    * More primality tests.
    * Wrapped is\_even and is\_odd.
    * Cached hash values to improve performance.
    * Improved random number support.
    * Added "slice" access to the bits of an **mpz** and **xmpz**. Bit manipulations work in-place on **xmpz**.
    * Renamed the bit manipulation methods; i.e. **gmpy.scan1** is now **gmpy2.bit\_scan1**.

# Which version to use? #

**gmpy2** is now the recommended version, especially if you use the pre-compiled versions for Windows.

If you are compiling from source, **gmpy2** is still the recommended version. However, **gmpy2** requires recent versions of GMP, MPFR, and MPC and therefore **gmpy2** may be more complicated to build. If you just need  fast integer or rational arithmetic, you can use **gmpy**. The performance difference between **gmpy** and **gmpy2** for integer and rational arithmetic is negligible.