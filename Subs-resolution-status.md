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
Inheritance is partially implemented, refactoring of object methods better not to use yet.

## What is planned
* Subs annotations usage to resolve chained invocations like `$obj->method1->method2->method3`
* Annotation files, to be able to define return values and prototypes for packages without those.
* Resolving constants
* Resolving imports
* Optimizing inheritance search