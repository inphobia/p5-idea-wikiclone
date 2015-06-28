One of the most important goals of this plugin was to unleash powerful IDEA refactoring into the Perl's world. But, it's easier to say... :)

## Currently
At the moment, only obvious subs invocations are resolved:
* `sub()`
* `Package::sub()`
* `sub Package()` - works, but glitchy and not recommended
* `$self->sub()` - without inheritance
* `$obj->sub()` if `$obj` has been declared with specific type:
```
my Foo::Bar $obj;
...
$obj->method(); # we know that it's Foo::Bar method
```
Again, without inheritance.

## What is planned
* MRO implementation to resolve inherited subs and `SUPER::` calls
* Subs annotations usage to resolve chained invocations like `$obj->method1->method2->method3`