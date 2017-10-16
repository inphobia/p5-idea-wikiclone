Camelcade introduces annotations, these annotations adds a meta-information to your code, helping the plugin to assist you better in your daily work.

## #@deprecated
```
#@deprecated
sub some_deprecated_sub { ... }

#@deprecated
my $var;

#@deprecated 
package Foo::Bar;
```
Such sub, variable or a namespace will be stroke out everywhere in your project sources. 

# Literals annotations
## #@inject 
Allows you to inject other languages into the string contents. Like:
```
#@inject MYSQL
my $sql = 'SELECT UNIX_TIMESTAMP()`;
```
If your IDE supports MYSQL language, you'll have an autocompletion, navigation and re-factoring in your string.
This annotation should be just before the string or before the statement containing the string.
If you are using here-docs, it's not necessary to annotate them, you may just use a language identifier as a here-doc marker:
```
my $sql = <<MYSQL
SELECT UNIX_TIMESTAMP()
MYSQL
```

# Variables annotations
## #@type
Perl has it's own syntax to specify a variable type in declaration:
```
my Foo::Bar $var;
```
But, it has some flaws: 
* You can't specify different types for multiple variables declaration `my Foo::Bar ($var1, $var2..)`
* You can't specify tricky types, like arrayref of objects. This is not yet supportet in the plugin too, but going to be.
* You are forced to use a slower version of unpacking variables via `shift`, instead of faster `my ($var1, $var2, ..) = @_` if you need to unpack variables of different types.
* The namespace must be loaded before typing with perl syntax, e.g `use Foo::Bar; my Foo::Bar $var`.

This is where `#@type` annotation may be used:
```
my ( 
    $var1, 
    $var2,
    #@type Foo::Bar
    $var3 
) = @_;
```
This annotation will tell the plugin that `$var3` contains a reference to the `Foo::Bar` object. Annotation may be just before a variable in declaration or before a declaration expression.

The plugin using following priority:

1. Annotation before the variable.
2. Annotation before the declaration expression.
3. Perl variable type in declaration.
4. Implicit variable type from assignment, like `$var = foo_bar_getter();`, if `foo_bar_getter` is annotated with `#@returns Foo::Bar` (see below).

# Subs annotations
## #@returns
```
#@returns Foo::Bar
sub foo_bar_getter { ... }
```
Specify sub return value class.

`new` is implicitly annotated with package it's invoked for.

```
#@returns *
sub self_getter{ ... }
```
Means that method always returns `$self`

## #@method
```
#@method
sub get_something{ return shift->{something};}
```
The plugin has some heuristic to distinct static subs from methods, but it's impossible to handle all situations in Perl. When the plugin fails to detect that a sub is a method, you may hint it with `#@method` annotation. Methods will appear in object autocompletion, after `->` operator and statics appears only in static auto-completion, after `::`. Resolving and navigations doesn't care if this is a static sub or method.
