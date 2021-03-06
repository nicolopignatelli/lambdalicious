# Lambdalicious

Experiments in Elegant Functional Programming in PHP

![Lambda Man by Martin Grabmüller](lambda-man.jpg "Lambda Man by Martin Grabmüller")

[![Build Status](https://travis-ci.org/mathiasverraes/lambdalicious.svg)](https://travis-ci.org/mathiasverraes/lambdalicious)

## Design Goals

- LISPy Love for Lists!
- Higher order Happiness!
- Posh Partial Application!
- Gloriously Global!

## Example

```php
<?php
$accounts = [
    pair('Jim', 100),
    pair('Jenny', 30),
    pair('Jack', -50),
    pair('Jules', -43),
];

$negate = multiply(-1);
$totalOutstanding = pipe( // think *nix pipes and filters
    map(second, __), // __ is a partial application placeholder. second returns the second item in a Pair
    filter(lt(__, 0), __), // lt is less than
    reduce(add, __, 0),
    $negate
);

assert( $totalOutstanding($accounts) == 93 );
```

Find more in the `examples` folder, or read the tests.

## FAQ

**What is this all about?**

Read the [The Little Schemer](http://www.amazon.com/gp/product/0262560992/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=0262560992&linkCode=as2&tag=verraesnet-20&linkId=LWAZ2Z4LXEVNZNAH).
Or learn LISP (or Clojure or some variant). There's also some Erlang-ish ideas in there.

**Wait but why?**

Why did I try to build a radio when I was ten? Why did I take apart my father's computer when I was eleven?

**But but but... Global functions? Global constants?**

You're very observant! Don't think of it as polluting the global namespace. Think of it as cleaning up the global namespace!

**Can you backport it to older PHP versions?**

Boring, next question please.

**Wouldn't this all be a lot easier and more elegant using HHVM/Hack?**

I know right? HHVM doesn't support some of the extensions I need.

**Should I use it in production?**

Yes! Be a pioneer, be an early adopter, be an innovator! Show your boss you *can* take risks on company time! You are a
strong individual who makes your own decisions, even in the face of constant change and breakage! You are a legend!

**I want to contribute!**

I like you already!

