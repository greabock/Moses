[![Build Status](https://travis-ci.org/Yonaba/Moses.png)](https://travis-ci.org/Yonaba/Moses)
[![License](http://img.shields.io/badge/Licence-MIT-brightgreen.svg)](LICENSE)
[![Lua](https://img.shields.io/badge/Lua-5.1%2C%205.2%2C%205.3%2C%20JIT-blue.svg)]()

A Lua utility-belt library for [functional programming](http://en.wikipedia.org/wiki/Functional_programming).<br/>

## Examples

How can I get the sum of all integers between 1 and 100 ?

```lua
local sum = M.sum(M.range(100))
print(sum) -- 5050
````
Say I am looking for the length of the longest word in some array ?

```lua
local words = {'some','words','of','different','lengths'}
print(M.max(words, M.op.length)) -- 9 letters
````

What is the sum of all fibonacci numbers for n below or equal 25 ?

```lua
local function fib(n) return n < 2 and n or fib(n - 1) + fib(n - 2) end
local fibsum = M.sum(M.map(M.range(25), fib))
print(fibsum) -- 196417
````

Or let us do the same, opbject-oriented style with chaining :

```lua
local function fib(n) return n < 2 and n or fib(n - 1) + fib(n - 2) end
local fibsum = M.chain(M.range(25)):map(fib):sum():value()
print(fibsum) -- 196417
````

Or even shorter :

```lua
local fibsum = M(M.range(25)):map(fib):sum():value()
print(fibsum) -- 196417
````

Feel free to download and try it on your own!

## Download

### Archive
* __zip__: [1.6.1 (stable)](http://github.com/Yonaba/Moses/archive/Moses-1.6.1-1.zip) | [dev](http://github.com/Yonaba/Moses/archive/master.zip) | [all releases](http://github.com/Yonaba/Moses/tags)
* __tarball__: [1.6.1 (stable)](http://github.com/Yonaba/Moses/archive/Moses-1.6.1-1.tar.gz) | [dev](http://github.com/Yonaba/Moses/archive/master.tar.gz) | [all releases](http://github.com/Yonaba/Moses/tags)

### Bash

```bash
git clone git://github.com/Yonaba/Moses.git
````

### LuaRocks
```
luarocks install moses
````

### MoonRocks

```bash
moonrocks install moses
````

## Usage

```lua
local _ = require "moses"
````

*Note:* the full source [moses.lua](https://github.com/Yonaba/Moses/blob/master/moses.lua) is quite heavy (~83 kiB, 2780 LOC). You can alternatively use the [minified version](https://github.com/Yonaba/Moses/blob/master/moses_min.lua) (~32 kiB, 521 LOC).

## Tutorial

Find a complete set of code examples in [tutorial.md](https://github.com/Yonaba/Moses/blob/master/doc/tutorial.md).
  
## Documentation

* See *doc* folder : [doc](https://github.com/Yonaba/Moses/blob/master/doc)
* Or browse it online : see [online doc](http://yonaba.github.io/Moses/doc).

## Credits and Acknowledgement

* [Jeremy Ashkenas](https://github.com/jashkenas), for the amazing [Underscore.js](http://documentcloud.github.com/underscore/)
* [Marcus Irven](http://mirven.github.com/underscore.lua/)'s and [JT Archie](https://github.com/jtarchie/underscore-lua)'s 1-to-1 ports that also inspired this
* [Matthew Rocklin](https://github.com/mrocklin)'s [Toolz](https://github.com/pytoolz/toolz/) from which I borrowed some ideas
* [Steve Donovan](https://github.com/stevedonovan)'s [LDoc](https://github.com/stevedonovan/ldoc/), used to generate the current HTML documentation.
* [Mark Langen](https://github.com/stravant)'s [LuaMinify](https://github.com/stravant/LuaMinify/), used to generate a minified version of this library.

## Specification

Run [spec tests](https://github.com/Yonaba/Moses/blob/master/spec) from Lua using [busted](https://github.com/Olivine-Labs/busted/) with the following command from the root folder:

````
busted
````

## License

This work is under [MIT-LICENSE](http://www.opensource.org/licenses/mit-license.php)<br/>
Copyright (c) 2012-2018 Roland Yonaba. <br/>
See [LICENSE](LICENSE).


