Camelcade introduces subs annotaions, which can help you to maintain your code and help Camelcade to resolve subs properly. 

# #@deprecated
```
#@deprecated
sub some_deprecated_sub { ... }
```
Such sub will be stroke out everywhere in your project sources. This annotation is also supported for packages definition.

# #@returns
```
#@returns Foo::Bar
sub foo_bar_getter { ... }
```
Specify sub return value.

`new` is implicitly annotated with package it's invoked for.

# #@method
```
#@method
sub get_something{ return shift->{something};}
```
Basically, plugin distincts methods from subs by it's first argument. If it's `$proto`, `$class`, or `$self` - it's a method, and static sub otherwise. But, sometimes you may have method which does not need `$self`, so you may force plugin to treat it as a method by this annotation.