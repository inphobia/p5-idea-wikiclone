There are some known issues, which currently planned to fix.

##Packages refactoring
In last few builds packages refactoring is not working well. use/require occurrences are not being updated properly. Plugin may do most of the work for you, but manual checking required.

##Subs refactoring
You may safely refactor static methods, like `Foo::Bar::method`. Objects methods resolution is still in development and can't be reliably refactored. Plugin may do most of the work for you, but manual checking required.

##Variables refactoring
Because variables in qq strings and regexes are not interpolated yet, you should be careful with variables refactoring (such variables won't be changed). Plugin may do most of the work for you, but manual checking required.

##Large files performance
Editing of files larger than 100kb may be laggy. Problem is still not localized.

##Heredoc live template
When inserting heredoc live template from indented position, closing marker is indented too. 

##Recovery of heavy braced statements
Because braces in Perl are used for almost everything: blocks, hashes, variable names, quotes; statements error recovery may be glitchy. It looks like file parsing and highlighting falls apart after error in such statement. 
