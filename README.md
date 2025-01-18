
Traits
======

Traits for TypeScript Classes

<p/>
<img src="https://nodei.co/npm/@rse/traits.png?downloads=true&stars=true" alt=""/>

<p/>
<img src="https://david-dm.org/rse/@rse/traits.png" alt=""/>

About
-----

This is a small TypeScript library providing a Trait (aka Mixin)
facility for extending classes with multiple base functionalities.

Installation
------------

```shell
$ npm install @rse/traits
```

Usage
-----

```ts
import { Trait, Derive } from "@rse/traits"

const Swim = Trait((base) => class Swim extends base {
    swimmed = 0
    swim () { return this.swimmed++ }
})
const Walk = Trait((base) => class Walk extends base {
    walked = 0
    walk () { return this.walked++ }
})
class Sample extends Derive(Swim, Walk) {
    perform () {
        console.log(this.swim())
        console.log(this.walk())
        console.log(this.swim())
        console.log(this.walk())
        console.log(this.swim())
        console.log(this.walk())
    }
}

const sample = new Sample()
sample.perform()
```

```
$ npx tsx sample.js
0
0
1
1
2
2
```

History
-------

The **@rse/traits** library was developed in January 2025 by Dr. Ralf
S. Engelschall. It is heavily inspired by the API and type tricks of
**@ddd-ts/traits**, although it is a "from scratch" implementation
as the complexity of constructor properties were not wished for
**@rse/traits** and there should have been especially no API usage
difference between generic and concrete traits.

License
-------

Copyright &copy; 2025 Dr. Ralf S. Engelschall (http://engelschall.com/)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

