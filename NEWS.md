# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

For pre-1.0.0 releases we will increment the minor version when we export any new functions or alter exported API.
For bug fixes, performance enhancements, or fixes to unexported functions we will increment the patch version.
**Note**: The exported API can be considered very stable and likely will not change without serious consideration.

# Unreleased

### Fixed
- Improved inference in `sphericalbesselj`. ([PR #61](https://github.com/JuliaMath/Bessels.jl/pull/61)). Contributed by **@Samuel3008**.

# Version 0.2.5

### Fixed
- Fix bug for very large inputs (x>1e16) in besselj0 and friends routines. A particularly thank you to @jwscook for reporting the bug in ([Issue #53](https://github.com/JuliaMath/Bessels.jl/pull/56)) and providing a very detailed analysis.


# Version 0.2.4

### Added
- Enable auto-vectorization of asymptotic expansions to improve performance. This reduces computation time around ~20% in some domains ([PR #45](https://github.com/JuliaMath/Bessels.jl/pull/45)).

# Version 0.2.3

### Added
- Add support for nu isa AbstractRange (i.e., `besselj(0:10, 1.0)`) to allow for fast computation of Bessel functions at many orders ([PR #53](https://github.com/JuliaMath/Bessels.jl/pull/53)).

# Version 0.2.2

### Added
 - Support for all airy functions and derivatives in entire complex plane ([PR #51](https://github.com/JuliaMath/Bessels.jl/pull/51)). These are specialized routines for airy functions instead of relying on connection to besselk. These are a couple digits more accurate and faster than previous versions.

# Version 0.2.1

### Added
 - Add more optimized methods for Float32 calculations that are faster ([PR #43](https://github.com/JuliaMath/Bessels.jl/pull/43))
 - Add methods for computing modified spherical bessel function of second ([PR #46](https://github.com/JuliaMath/Bessels.jl/pull/46) contributed by @cgeoga and first ([PR #47](https://github.com/JuliaMath/Bessels.jl/pull/47))) kind. These functions are currently not exported. Closes ([Issue #25](https://github.com/JuliaMath/Bessels.jl/issues/25))
 - Asymptotic expansion for x >> nu was added ([PR #48](https://github.com/JuliaMath/Bessels.jl/pull/48)) that decreases computation time for large arguments. Contributed by @cgeoga

### Fixed
 - Reduce compile time and time to first call of besselj and bessely ([PR #42](https://github.com/JuliaMath/Bessels.jl/pull/42))

# Version 0.2.0

### Added
 - add an unexport method (`Bessels.besseljy(nu, x)`) for faster computation of `besselj` and `bessely` (#33)
 - add exported methods for Hankel functions `besselh(nu, k, x)`, `hankelh1(nu, x)`, `hankelh2(nu, x)` (#33)
 - add exported methods for spherical bessel function `sphericalbesselj(nu, x)`, `sphericalbesselj(nu, x)`, (#38)
 - add exported methods for airy functions `airyai(x)`, `airyaiprime(x)`, `airybi(x)`, `airybiprime(x)`, (#39)

### Fixed
 - fix cutoff in `bessely` to not return error for integer orders and small arguments (#33)
 - fix NaN return for small arguments (issue [#35]) in bessely (#40)
 - allow calling with integer argument and add float16 support (#40)

# Version 0.1.0

Initial release of Bessels.jl

### Added

 - support bessel functions (`besselj`, `bessely`, `besseli`, `besselk`) for real arguments
 - provide a gamma function (`Bessels.gamma`) for real arguments
