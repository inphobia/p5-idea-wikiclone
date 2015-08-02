Here is the list of features, currently implemented in the Camelcade (don't forget to check [known issues](https://github.com/hurricup/Perl5-IDEA/wiki/Known-issues)):

* Perl5 lexing and parsing. As soon as it's not a port of native Perl5 lexer/parser, it may have some bugs. If you've encountered situation, where your code is not being parsed properly, feel free to create an issue with code example. 
  * Currently supported languages are Perl5, POD, [Mojolicious templates](https://github.com/hurricup/Perl5-IDEA/wiki/Mojolicious-support) and php-style Perl5 (Embedded perl)
* Perl5 interpreter (SDK) and Perl5 module type support. You should add Perl5 interpreter as project SDK to give Camelcade access to installed packages. [More..](https://github.com/hurricup/Perl5-IDEA/wiki/Getting-started)
* Syntax highlighting. Perl and POD sources are highlighted and there is a Default theme, taken from NP++. There is no Darcula theme in the plugin jar.
  * Color settings dialog example is still buggy and doesn't show some syntax constructions ([TBF](https://github.com/hurricup/Perl5-IDEA/issues/215)).
* Brace matching, code folding, quote handling, live templates for Perl5.
* Create Perl5 file context menu actions.
* Lexical and global variables auto-completion, navigation and refactoring.
* Packages auto-completion, navigation and refactoring.
* Subs auto-completion, navigation and refactoring are only partially implemented. See [current subs resolution status] (https://github.com/hurricup/Perl5-IDEA/wiki/Subs-resolution-status).
* Heredoc markers navigation and refactoring.
* [Subs annotations] (https://github.com/hurricup/Perl5-IDEA/wiki/Subs-annotations)
* Intentions 
  * Convert string to here-doc
* Code inspections: 
  * Packages
    * Missing package file
    * Undefined namespace
    * Multiple namespace definitions
    * Namespace clash with core namespace
    * Missing strict pragma
    * Missing warnings pragma
  * Subs
    * Deprecated sub
    * Undefined and undeclared sub 
    * Multiple sub definitions/declarations
    * Fancy method call: `method Package()` with quickfix suggested to change to `Package->method()`
  * Variables
    * Undeclared variable
    * Shadowing
    * Lexical built-in declaration
    * Unused lexical variables 
* IntelliLang integration. Heredoc texts may be automatically injected with other language, depending on marker text. To make this work, IntelliLang plugin must be enabled and appropriate Language supported by IDEA natively or via plugin. Following markers are currently supported:
  * JavaScript: JS, JS15, JS16, JS17, JS18, APPLEJS
  * Database: SQL, MYSQL, PGSQL, TSQL, OSQLP, DB2, SQL92, SQLITE, SYBASE, HSQLDB, GSQL, OSQL (Both Database navigator and JetBrains Database tools are supported)
  * Web-related: JSON, CSS, DTD, XHTML, XML, HTML
  * Templating: EPERL5, MOJO
  * Misc: JAVA, YAML, MANIFEST, PHP, PYTHON, PERL5