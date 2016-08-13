# External Annotations

Namespaces and subs annotations are pretty useful in my daily coding. They allows to help plugin to resolve names 
properly, make object oriented auto-completion possible, allows deprecating things for myself and collegues.

But once you've got used to them, you may need to install and extensively use some CPAN module which is not annotated.

And this is really... uncomfortable. There are few ways to handle this situation, but all of them has their flaws.

This is why exernal annotations has been made in 2.300 release.

# Basics

Plugin supports external annotations files with `*.pmea` extension (Perl module external annotation). These files using limited
Perl syntax:
```
package Foo::Bar;
	
sub somemethod;
```	
That's all. Only two types of statements. Semicolon-ended package "declaration" and sub "declaration". Sub MUST always 
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
Using this mechanism you may annotate any package, even installed from CPAN, without altering foreign sources or making 
pseudo-source file with annotated declarations.

# Annotations Levels

There are three levels of external annotations, located in three different directories:

* Plugin level. These files are shipped with the plugin and should not be edited by user. This annotations located in plugin installation directory.
* Application level. If you want to annotate some package installed on your machine for every project you've got - this is what you need. Annotate once and use in every project you have. Path to application annotations is configurable. 
* Project level. Sometimes you may have some nuances in your specific project, like deprecation of some module. In this case, you may use a project-level annotations to do it. Project level annotations path is configurable but must be inside your project root.

# Resolution Order

When plugin attempts to find an annotation for sub or namespace definition, it will check all sources in following order (first wins):

1. Declaration itself
2. Project-level external annotations
3. Application-level external annotations
4. Plugin-level external annotations

So if you have a Plugin-level annotation and it is wrong for some reason, you may annotate on project/application level and plugin annotation will be totally ignored.

# Toolbox

Aside of supporting annotations, plugin provides few useful tools to annotate your code.

Annotated subs and namespaces will have an `@` icon on the gutter, which can navigate you to any available annotation:

![Screenshot](https://github.com/Camelcade/Perl5-IDEA/blob/master/images/ea/gutter.png)

Sub names and package names have intentions to annotate on any available level:

![Screenshot](https://github.com/Camelcade/Perl5-IDEA/blob/master/images/ea/intentions.png)

Annotations files has gutter icons to navigate between levels and syntax autocompletion, including available namespaces and subs:

![Screenshot](https://github.com/Camelcade/Perl5-IDEA/blob/master/images/ea/completion.png)
