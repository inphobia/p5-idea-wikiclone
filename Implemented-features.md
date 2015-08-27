Here is the list of features, currently implemented in the Camelcade (don't forget to check [known issues](https://github.com/hurricup/Perl5-IDEA/wiki/Known-issues)):

* Perl5 lexing and parsing. As soon as it's not a port of native Perl5 lexer/parser, it may have some bugs. If you've encountered situation, where your code is not being parsed properly, feel free to create an issue with code example. 
  * Currently supported languages are Perl5, POD, [Mojolicious templates](https://github.com/hurricup/Perl5-IDEA/wiki/Mojolicious-support) and php-style Perl5 (Embedded perl)
* Perl5 interpreter (SDK) and Perl5 module type support. You should add Perl5 interpreter as project SDK to give Camelcade access to installed packages. [More..](https://github.com/hurricup/Perl5-IDEA/wiki/Getting-started)
* Syntax highlighting. Perl and POD sources are highlighted and there is a Default theme, taken from NP++. 
  * Color settings dialog example is still buggy and doesn't show some syntax constructions ([TBF](https://github.com/hurricup/Perl5-IDEA/issues/215)).
* Interpolation in appropriate strings, here-docs and regexps.
  * NB:
    * Code interpolation is still lame, and may show that it's ok in places where it is not.
    * Regex interpolation can't distinct array element from scalar with character group after it.
    * Here-doc language injection is automatically turned off in QQ/QX heredoc if there is at least one variable.
* Brace matching, quote matching, regex delimiters matching, code folding, quote handling, live templates for Perl5.
* Go to symbol navigation for: subs, constants, packages and global variables.
* File structure view
* Class hierarchy view
* Subs auto-completion, navigation and refactoring. See [current subs resolution status] (https://github.com/hurricup/Perl5-IDEA/wiki/Subs-resolution-status).
* Inherited subs resolution, auto-completion and refactoring (both `dfs` and `c3` mros supported)
* Imported subs and variables resolution, auto-completion and refactoring (re-factoring requires polishing, export/import arguments are not being refactored only declaration and usage)
* AUTOLOAD-ed methods and subs resolution and decoration (atm. AUTOLOAD must be defined as a sub, not a named block).
* Create Perl5 file context menu actions.
* Lexical and global variables auto-completion, navigation and refactoring.
* Global variables declaration with `use vars`
* Packages auto-completion, navigation and refactoring.
* Heredoc markers navigation and refactoring.
* [Subs and packages annotations] (https://github.com/hurricup/Perl5-IDEA/wiki/Subs-annotations)
* Intentions 
  * Convert string to here-doc
* Code inspections: 
  * Packages
    * Missing package file
    * Undefined namespace
    * Multiple namespace definitions
    * Namespace clash with core namespace
    * Missing `strict` pragma
    * Missing `warnings` pragma
  * Subs
    * Deprecated sub
    * Undefined and undeclared sub 
    * Multiple sub definitions/declarations
    * Fancy method call: `method Package()` with quickfix suggested to change to `Package->method()`
    * Unused subs/typeglobs (disabled by default, got performance issues on large files and common subs names)
  * Variables
    * Undeclared variable
    * Shadowing
    * Lexical built-in declaration
    * Unused lexical variables 
    * Unused global variables 
* IntelliLang integration. Heredoc texts may be automatically injected with other language, depending on marker text. To make this work, IntelliLang plugin must be enabled and appropriate Language supported by IDEA natively or via plugin. Following markers are currently supported:
  * JavaScript: JS, JS15, JS16, JS17, JS18, APPLEJS
  * Database: SQL, MYSQL, PGSQL, TSQL, OSQLP, DB2, SQL92, SQLITE, SYBASE, HSQLDB, GSQL, OSQL (Both Database navigator and JetBrains Database tools are supported)
  * Web-related: JSON, CSS, DTD, XHTML, XML, HTML
  * Templating: EPERL5, MOJO
  * Misc: JAVA, YAML, MANIFEST, PHP, PYTHON, PERL5
* IDEA extensions
  * Extension point for package processors and set of interfaces to implement custom package processors (like `Mojo::Base` which is `strict`+`v5.10`+`base`)