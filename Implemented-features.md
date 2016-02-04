Here is the list of features, currently implemented in the Camelcade (don't forget to check [known issues](https://github.com/hurricup/Perl5-IDEA/wiki/Known-issues)):

* Perl5 lexing and parsing. As soon as it's not a port of native Perl5 lexer/parser, it may have some bugs. If you've encountered situation, where your code is not being parsed properly, feel free to create an issue with code example. 
* Currently supported languages are Perl5, POD, and some extensions:
  * [Class::Accessor](http://search.cpan.org/~kasei/Class-Accessor/lib/Class/Accessor.pm) api 
  * [Exporter](https://github.com/hurricup/Perl5-IDEA/wiki/Exporter-support)
  * [Mason2](https://github.com/hurricup/Perl5-IDEA/wiki/Mason2-support)
  * [Method::Signatures::Simple](http://search.cpan.org/dist/Method-Signatures-Simple/lib/Method/Signatures/Simple.pm) - `method` and `func`
  * [Mojolicious templates](https://github.com/hurricup/Perl5-IDEA/wiki/Mojolicious-support) 
  * [Moose](https://github.com/hurricup/Perl5-IDEA/wiki/Moose-support)
  * Php-style Perl5 (Embedded perl)
  * [Switch](http://perldoc.perl.org/5.8.8/Switch.html) core module
* Miscellaneous
  * Syntax highlighting. Perl and POD sources are highlighted and there is a Default theme, taken from NP++. 
  * Interpolation in appropriate strings, here-docs and regexps.
  * Brace matching, quote matching, regex delimiters matching, code folding, quote handling.
  * File structure view
  * Class hierarchy view
  * [Subs and packages annotations] (https://github.com/hurricup/Perl5-IDEA/wiki/Subs-annotations)
  * Perl5 interpreter (SDK) and Perl5 module type support. You should add Perl5 interpreter as project SDK to give Camelcade access to installed packages. [More..](https://github.com/hurricup/Perl5-IDEA/wiki/Getting-started)
* Configuration
  * Run configurations for Perl scripts
  * Self-object reference variable names
  * Automatic language injection in here-doc 
* Navigation & Refactoring
  * Gutter navigation to super/sub classes
  * Gutter navigation to super/inner class methods
  * Go to symbol navigation for: subs, constants, packages and global variables
  * Go to declaration navigation for subs, variables, packages and here-doc markers. See [current subs resolution status] (https://github.com/hurricup/Perl5-IDEA/wiki/Subs-resolution-status).
  * Both `dfs` and `c3` mros supported for methods resolution
  * AUTOLOADed methods may be resolved, if AUTOLOAD declared as a named block, not sub
  * All navigatable entities can be refactored
* Completion and Smart Keys
  * Quote handler for regex and quote-like operators
  * Variables, subs/methods and packages auto-completion
  * Auto-suggestion of names for here-doc markers, variables and subs/methods
  * Auto-completion of hash indexes (dumb one, offers seen strings)
  * Live templates for Perl5 constructions and test scripts macroses.
* Code style and formatter:
  * Perl5-specific CodeStyle settings panel.
  * Spacing settings for perl code.
  * Optional quotes automatic insertion/removing. NB: numeric values are not quoted/unquoted.
  * Optional dereference insertion/removing between hash/array indexes.
  * Optional parentheses insertion/removing in statement modifiers.
  * Conversion `$var->{key}` to `$$var{key}` and vice versa.
  * Conversion `@$array_ref` to `@{$array_ref}` and vice versa (does not affects hash/array elements or slices).
  * Conversion `main::` to `::` and vice versa.
* Code Generation
  * Actions to generate getters and setters
  * Action to generate class constructor
  * Action to override method of parent class
  * Create Perl5 scripts, packages, tests and templates context menu actions.
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
    * File level variables inspection. (Pretty useful while migrating from CGI to some persistent environment)
* IntelliLang integration. Heredoc texts may be automatically injected with other language, depending on marker text. To make this work, IntelliLang plugin must be enabled and appropriate Language supported by IDEA natively or via plugin. Following markers are currently supported:
  * JavaScript: JS, JS15, JS16, JS17, JS18, APPLEJS
  * Database: SQL, MYSQL, PGSQL, TSQL, OSQLP, DB2, SQL92, SQLITE, SYBASE, HSQLDB, GSQL, OSQL (Both Database navigator and JetBrains Database tools are supported)
  * Web-related: JSON, CSS, DTD, XHTML, XML, HTML
  * Templating: EPERL5, MOJO
  * Misc: JAVA, YAML, MANIFEST, PHP, PYTHON, PERL5
* IDEA extensions
  * Extension point for package processors and set of interfaces to implement custom package processors (like `Mojo::Base` which is `strict`+`v5.10`+`base`)
