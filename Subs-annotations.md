Camelcade introduces subs annotaions, which can help you to maintain your code and help Camelcade to resolve subs properly. 

# #@deprecated
```
#@deprecated
sub some_deprecated_sub { ... }
```
Such sub will be stroke out everywhere in your project sources.

# #@returns
```
#@returns Foo::Bar
sub foo_bar_getter { ... }
```
Specify sub return value.

`new` is implicitly annotated with package it's invoked for.
