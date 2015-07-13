There are some known issues, which currently planned to fix.

##Large files performance
Editing of files larger than 100kb may be laggy. Problem is still not localized.

##Heredoc live template
When inserting heredoc live template from indented position, closing marker is indented too. 

##Recovery of heavy braced statements
Because braces in Perl are used for almost everything: blocks, hashes, variable names, quotes; statements error recovery may be glitchy. It looks like file parsing and highlighting falls apart after error in such statement. 
