One of the most important goals of this plugin was to unleash powerful IDEA refactoring into the Perl's world. But, it's easier to say... :)

## Currently
At the moment, only obvious subs invocations are resolved:
* `sub()` - for defined/declared/imported subs or typeglobs.
* `Package::sub()`  - for defined/declared/imported subs or typeglobs.
* `Package->sub()` - with inheritance
* `sub Package()` - works, but glitchy, not recommended
* `$self->sub()` - with inheritance
* `SUPER::sub()` - with inheritance
* `$obj->sub()` - with inheritance, if `$obj` has been declared with specific type or assigned to sub return value with known result.
```
my Foo::Bar $obj;
...
$obj->method(); # we know that it's Foo::Bar method

my $other_obj = Foo::Baz->new();

$other_obj->method(); # we know that it's a Foo::Baz method

```
* `Foo::Bar->new->method->other_method` - with inheritance. To make this work, methods should be [annotated](https://github.com/hurricup/Perl5-IDEA/wiki/Subs-annotations) with `#@returns`.

## What is planned
* Proper resolve for lexical subs. For now they are treated as regular ones
* Implement and improve heuristic to understand Perl code
* Annotation files, to be able to define return values and prototypes for packages without them 
* subs annotations for structures of objects, like: 
  * `#@returns [Foo::Bar]` - returns arrayref of `Foo::Bar` objects
  * `#@returns {Foo::Bar}` - returns hashref with `Foo::Bar` objects as values
