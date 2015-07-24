One of the most important goals of this plugin was to unleash powerful IDEA refactoring into the Perl's world. But, it's easier to say... :)

## Currently
At the moment, only obvious subs invocations are resolved:
* `sub()`
* `Package::sub()`
* `Package->sub()` - with inheritance
* `sub Package()` - works, but glitchy, not recommended
* `$self->sub()` - with inheritance
* `SUPER::sub()` - with inheritance
* `$obj->sub()` - with inheritance, if `$obj` has been declared with specific type:
```
my Foo::Bar $obj;
...
$obj->method(); # we know that it's Foo::Bar method
```
* `Foo::Bar->new->method->other_method` - with inheritance. To make this work, methods should be [annotated](https://github.com/hurricup/Perl5-IDEA/wiki/Subs-annotations) with `#@returns`.

Inheritance is partially implemented, refactoring of object methods better not to use yet.

## What is planned
* Implement and improve heuristic to understand Perl code:
```
my $foo_bar = Foo::Bar->new();
...
$foo_bar->method();  # we should know that it's a method of Foo::Bar
```
* Annotation files, to be able to define return values and prototypes for packages without those.
* Resolving constants
* Resolving imports
* Optimizing inheritance search