There are some known issues, which currently planned to fix.

## Compatibility with JB products
Because of my mistake in the beginning of plugin development, i've used several features that are missing in all products but IDEA itself. So, plugin currently works as intended only in IDEA Community and IDEA Ultimate. This problem is [planned to be fixed](https://github.com/hurricup/Perl5-IDEA/issues/265) before release. 

In other products, like PHPStorm, PyCharm, etc, it may work or may not (even may break main product functionality while enabled).

##Subs refactoring
You may safely refactor static methods, like `Foo::Bar::method`. Objects methods resolution is still in development and can't be reliably refactored. Plugin may do most of the work for you, but manual checking required.

##Package files refactoring
There is a smart mechanism, which allows you to move/rename package files and nested namespaces will be automatically renamed with their usages. But, sometimes it misses something. Anyway - it will do most of the work.

##Unused subs and vars inspections
If sub or variable can't be resolved because of tricky usage or invocation, it will be annotated as unused. But be careful.

##Large files performance
Editing of files larger than 100kb may be laggy. Problem is still not localized.

##Heredoc live template
When inserting heredoc live template from indented position, closing marker is indented too. 

##Recovery of heavy braced statements
Because braces in Perl are used for almost everything: blocks, hashes, variable names, quotes; statements error recovery may be glitchy. It looks like file parsing and highlighting falls apart after error in such statement. 
