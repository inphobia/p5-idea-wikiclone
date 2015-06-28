There are some known issues, which currently planned to fix.

#Large files performance
Editing of files larger than 100kb may be laggy. Problem is still not localized.

#Heredoc live template
When inserting heredoc live template from indented position, closing marker is indented too. 

#Recovery of heavy braced statements
Because braces in Perl are used for almost everything: blocks, hashes, variable names, quotes; statements error recovery may be glitchy. It looks like file parsing and highlighting falls apart after error in such statement. 

#Perl is ambiguous
A lot of Perl syntax constructions are ambiguous:
* `/` may be division operator or regex beginning.
* `*` may be mul operator or typeglob sigil.
* `&` may be and operator or code sigil.
* `<` and > may be gt and lt operators or angle braces for <FH> reading.
* `%` may be mod operator or hash sigil.
* `:` may be a part of trenar operator `... ? ... : ...` or label declaration suffix.
* `UNIVERSAL::can` may refer to the package `UNIVERSAL::can` or to sub `can` in `UNIVERSAL` namespace.
* `word` may be a sub, a namespace, a package or a filehandle.
There is no any document describing what is what in which situation. Sometimes it's easy to decide what is what, and sometimes - not. If you encountered incorrect parsing - just create an issue with code example. Also see [code style seciton] (https://github.com/hurricup/Perl5-IDEA/wiki/Code-style).