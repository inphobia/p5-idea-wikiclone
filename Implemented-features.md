Here is the list of features, currently implemented in the Camelcade:

* Perl5 lexing and parsing. As soon as it's not a port of native Perl5 lexer/parser, it may have some bugs. If you've encountered situation, where your code is not being parsed properly, feel free to create an issue with code example. 
* Perl5 interpreter (SDK) and Perl5 module type support. You should add Perl5 interpreter as project SDK to give Camelcade access to installed libraries. Library paths should be detected automatically and added to the classpaths.
*   If your project has it's own lib directory, you should add it as a Library in `File->Project structure->Modules->Your module->Dependencies`. All package names in use/require being resolved relatively to such library paths.