<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# erfcinvf

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Evaluate the [inverse complementary error function][erfcinv] for a single-precision floating-point number.

<section class="intro">

The [inverse complementary error function][erfcinv] is defined as

<!-- <equation class="equation" label="eq:inverse_complementary_error_function" align="center" raw="\operatorname{erfc}^{-1}(1-z) = \operatorname{erf}^{-1}(z)" alt="Inverse complementary error function."> -->

```math
\mathop{\mathrm{erfc}}^{-1}(1-z) = \mathop{\mathrm{erf}}^{-1}(z)
```

<!-- </equation> -->

where `erf^{-1}(z)` is the [inverse error function][@stdlib/math/base/special/erfinv].

</section>

<!-- /.intro -->

<section class="installation">

## Installation

```bash
npm install @stdlib/math-base-special-erfcinvf
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var erfcinvf = require( '@stdlib/math-base-special-erfcinvf' );
```

#### erfcinvf( x )

Evaluates the inverse complementary error function for a single-precision floating-point number.

```javascript
var y = erfcinvf( 0.5 );
// returns ~0.4769

y = erfcinvf( 0.8 );
// returns ~0.1791

y = erfcinvf( 0.0 );
// returns Infinity

y = erfcinvf( 2.0 );
// returns -Infinity
```

The domain of `x` is restricted to `[0,2]`. If `x` is outside this interval, the function returns `NaN`.

```javascript
var y = erfcinvf( -3.14 );
// returns NaN
```

If provided `NaN`, the function returns `NaN`.

```javascript
var y = erfcinvf( NaN );
// returns NaN
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var uniform = require( '@stdlib/random-array-uniform' );
var logEachMap = require( '@stdlib/console-log-each-map' );
var erfcinvf = require( '@stdlib/math-base-special-erfcinvf' );

var opts = {
    'dtype': 'float32'
};
var x = uniform( 100, 0.0, 2.0, opts );

logEachMap( 'x: %0.4f, erfcinvf(x): %0.4f', x, erfcinvf );
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/math/base/special/erfcinvf.h"
```

#### stdlib_base_erfcinvf( x )

Evaluates the inverse complementary error function for a single-precision floating-point number.

```c
float out = stdlib_base_erfcinvf( 0.5f );
// returns ~0.4769f

out = stdlib_base_erfcinvf( 0.8f );
// returns ~0.1791f
```

The function accepts the following arguments:

-   **x**: `[in] float` input value.

```c
float stdlib_base_erfcinvf( const float x );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

### Examples

```c
#include "stdlib/math/base/special/erfcinvf.h"
#include <stdio.h>

int main( void ) {
    const float x[] = { 0.0f, 0.22f, 0.44f, 0.67f, 0.89f, 1.11f, 1.33f, 1.56f, 1.78f, 2.0f };

    float v;
    int i;
    for ( i = 0; i < 10; i++ ) {
        v = stdlib_base_erfcinvf( x[ i ] );
        printf( "x: %f, erfcinvf(x): %f\n", x[ i ], v );
    }
}
```

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/math-base-special-erfcinvf.svg
[npm-url]: https://npmjs.org/package/@stdlib/math-base-special-erfcinvf

[test-image]: https://github.com/stdlib-js/math-base-special-erfcinvf/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/math-base-special-erfcinvf/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/math-base-special-erfcinvf/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/math-base-special-erfcinvf?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/math-base-special-erfcinvf.svg
[dependencies-url]: https://david-dm.org/stdlib-js/math-base-special-erfcinvf/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/math-base-special-erfcinvf/tree/deno
[deno-readme]: https://github.com/stdlib-js/math-base-special-erfcinvf/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/math-base-special-erfcinvf/tree/umd
[umd-readme]: https://github.com/stdlib-js/math-base-special-erfcinvf/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/math-base-special-erfcinvf/tree/esm
[esm-readme]: https://github.com/stdlib-js/math-base-special-erfcinvf/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/math-base-special-erfcinvf/blob/main/branches.md

[erfcinv]: https://en.wikipedia.org/wiki/Error_function#Inverse_functions

[@stdlib/math/base/special/erfinv]: https://github.com/stdlib-js/math-base-special-erfinv

<!-- <related-links> -->

<!-- </related-links> -->

</section>

<!-- /.links -->
