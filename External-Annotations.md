Namespaces and subs [annotations](https://github.com/hurricup/Perl5-IDEA/wiki/Subs-annotations) are pretty useful in my daily coding. They allow the plugin to resolve names 
properly, make object oriented auto-completion possible and allow deprecating things for myself and collegues.

But once you've gotten used to them, you might need to install and extensively use some CPAN module which is not annotated.

This can prove to be really... uncomfortable. There are several ways to handle this situation, but all of them has their own disadvantages.

For that reason we've introduced external annotations in 2.300 release.

# Basics

The plugin supports external annotation files with `*.pmea` extension (Perl module external annotation). These files are using limited
Perl syntax:
```
package Foo::Bar;
	
sub somemethod;
```	
That's all. There's only two types of statements. Semicolon-ended package "declaration" and sub "declaration". A sub MUST always 
have some package "declaration" above.

The most important thing, is that these "declarations" may be annotated with any appropriate annotations, like:
```
#@deprecated
package Foo::Bar;
	
#@method
#@returns Foo::Baz
sub somemethod;
```
Declaration word is quoted, because these are not real declarations. Only markers - which annotations to look here.
Using this mechanism you may annotate any package, even packages installed from CPAN, without altering foreign sources or making 
pseudo-source file with annotated declarations.

# Annotations Levels

There are three levels of external annotations, located in three different directories:

* Plugin level: These files are shipped with the plugin and should not be edited by user. This annotations are located in plugin installation directory.
* Application level: If you want to annotate a package installed on your machine for all of your projects - this would be the perfect usecase for it. Annotate once and use in all of your projects. The path to the application-level annotations is configurable. 
* Project level: Sometimes you may have some nuances in a specific project, like deprecation of some module. In this case, you may use a project-level annotations to do it. Project level annotations path is configurable but must be inside your project root.

# Resolution Order

When the plugin attempts to find an annotation for sub or namespace definition, it will check all the sources in following order (first match wins):

1. Declaration itself
2. Project-level external annotations
3. Application-level external annotations
4. Plugin-level external annotations

So, if you have a plugin-level annotation and it is wrong for some reason, you migth annotate on the project/application level and plugin annotation will be totally ignored.

# Toolbox

Aside from supporting annotations, the plugin provides quite a few useful tools to annotate your code.

Annotated subs and namespaces will have an `@` icon on the gutter, which can navigate you to any available annotation:

![Screenshot](https://github.com/Camelcade/Perl5-IDEA/blob/master/images/ea/gutter.png)

Sub names and package names have intentions to annotate on any available level:

![Screenshot](https://github.com/Camelcade/Perl5-IDEA/blob/master/images/ea/intentions.png)

Annotations themselves has gutter icons to navigate between levels and syntax autocompletion, including available namespaces and subs:

![Screenshot](https://github.com/Camelcade/Perl5-IDEA/blob/master/images/ea/completion.png)

# Contribution

If you've annotated a CPAN module for yourself, feel free to contribute your annotations to the plugin using pull-request. Annotations may be found [here](https://github.com/Camelcade/Perl5-IDEA/tree/master/annotations). Please, 
keep contributed annotations in the file-per-namespace format, e.g `Foo/Bar/Baz.pmea` for `Foo::Bar::Baz`. It's not required for plugin to work correctly, but will help to keep an order.