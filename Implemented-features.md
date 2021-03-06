Here is the list of features, currently implemented in the Camelcade (don't forget to check [known issues](https://github.com/hurricup/Perl5-IDEA/wiki/Known-issues)):

* Perl5 lexing and parsing (up to [5.26](https://github.com/Camelcade/Perl5-IDEA/releases/tag/2017.1.2)). As soon as it's not a port of native Perl5 lexer/parser, it may have some bugs. If you've encountered situation, where your code is not being parsed properly, feel free to create an issue with code example. 
* Currently supported languages are Perl5, POD, and some extensions:
  * [Class::Accessor](http://search.cpan.org/~kasei/Class-Accessor/lib/Class/Accessor.pm) API ([annotations](https://github.com/Camelcade/Perl5-IDEA/wiki/Annotations) supported).
  * [TryCatch](http://search.cpan.org/~ash/TryCatch/lib/TryCatch.pm) basic support. Currently `catch{}`, `catch($var){}` and `catch(Foo::Bar $var){}` are supported
  * [Method::Signatures::Simple](http://search.cpan.org/dist/Method-Signatures-Simple/lib/Method/Signatures/Simple.pm) - `method` and `func`
  * Php-style Perl5 (Embedded perl)
  * [Switch](http://perldoc.perl.org/5.8.8/Switch.html) core module
* Miscellaneous
  * Syntax highlighting. Perl and POD sources are highlighted and there is a Default theme, taken from NP++. 
  * Interpolation in appropriate strings, here-docs and regexps.
  * Brace matching, quote matching, regex delimiters matching, code folding, quote handling.
  * File structure view
  * Current context view
  * Class hierarchy view
  * [Subs, Variables and packages annotations](https://github.com/hurricup/Perl5-IDEA/wiki/Annotations)
  * Perl5 interpreter (SDK) and Perl5 module type support. You should add Perl5 interpreter as project SDK to give Camelcade access to installed packages. [More..](https://github.com/hurricup/Perl5-IDEA/wiki/Getting-started)
  * Spell checking in perl files
  * Scripts execution in the console 
* Configuration
  * Run configurations for Perl scripts
  * Self-object reference variable names
  * Automatic language injection in here-doc
* Dependencies
  * Plugin watches scripts output and in case missing package error, suggests to install a missing package with `cpan` or `cpanm`
  * Action to install an `App::cpanminus` (may be version-manager dependent, e.g. `perlbrew` installs one for all perls)    
  * Action to install an arbitrary packages
* Coverage support
  * You may run your scripts with coverage, using `Devel::Cover`  
* Navigation & Refactoring
  * Finding usages for built in namespaces, subs and variables
  * Gutter navigation to super/sub classes
  * Gutter navigation to super/inner class methods
  * Go to symbol navigation for: subs, constants, packages and global variables
  * Go to declaration navigation for subs, variables, packages, labels and here-doc markers. See [current subs resolution status](https://github.com/hurricup/Perl5-IDEA/wiki/Subs-resolution-status).
  * Both `dfs` and `c3` mros supported for methods resolution
  * AUTOLOADed methods may be resolved, if AUTOLOAD declared as a named block, not sub
  * All navigatable entities can be refactored
  * Class methods re-factoring with methods in subclasses and optionally in super-classes
* Completion and Smart Keys
  * Quote handler for regex and quote-like operators
  * Variables, subs/methods and packages auto-completion
  * Auto-suggestion of names for here-doc markers, variables and subs/methods
  * Auto-completion of hash indexes (dumb one, offers seen strings)
  * Live templates for Perl5 constructions and test scripts macroses.
  * Auto-completion for XSubs. To make it work they should be deparsed from the Perl5 settings or popup on IDE start.
* Code style and formatter:
  * Perl5-specific CodeStyle settings panel.
  * Spacing settings for perl code.
  * Optional quotes automatic insertion/removing. NB: numeric values are not quoted/unquoted.
  * Optional dereference insertion/removing between hash/array indexes.
  * Optional parentheses insertion/removing in statement modifiers.
  * Conversion `$var->{key}` to `$$var{key}` and vice versa.
  * Conversion `@$array_ref` to `@{$array_ref}` and vice versa (does not affects hash/array elements or slices).
  * Conversion `main::` to `::` and vice versa.
* Other Actions
  * Deparse file - deparses current file using `B::Deparse`.
  * Re-format with `Perl::Tidy` - reformats current file. By default `.perltidyrc` file in project root being used (see [Perl::Tidy](http://search.cpan.org/~shancock/Perl-Tidy/) documentation). You may specify additional command line arguments in the Perl5 settings.
* Code Generation
  * Actions to generate getters and setters
  * Action to generate class constructor
  * Action to override method of parent class
  * Create Perl5 scripts, packages, tests and templates context menu actions.
* Intentions 
  * Convert string to here-doc
  * Convert foreach loop to for loop, by [@brnrc](https://github.com/brnrc)
  * Convert a statement with modifier to the respective compound statement and vice versa  
* Documentation
  * POD support: live templates, completion, navigation, refactoring and few
useful inspections
  * Context help: hit Ctrl+Q on element in question and get your answer from
pod files or inline pod
* Code inspections:
  * Loops on hash inspection, see #1748
  * Loop control keywords inspection with quick-fixes, see #1747
  * Sub signatures positioning inspection. Checks if signature position conforms the selected target perl version with quickfixes (#1785).  
  * `Perl::Critic` annotations. By default `.perlcriticrc` file from project root or home dir being used (see [Perl::Critic](http://search.cpan.org/~thaljef/Perl-Critic/) documentation). You may specify additional command line arguments in the Perl5 settings.
  * Identifiers syntax for non-utf files
  * Labels
    * Undeclared and unresolved labels inspections
  * Packages
    * Missing package file with a quickfix to install package using `cpan` or `cpanm`
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
    * `use vars` deprecated declaration with a quick-fix to convert to `our` declaration. 
    * File level variables inspection. (Pretty useful while migrating from CGI to some persistent environment)
* IntelliLang integration. 
  * Heredoc texts may be automatically injected with other language, depending on marker text. To make this work, IntelliLang plugin must be 
  enabled and appropriate Language supported by IDEA natively or via plugin. Markers and languages are configurable in Perl5 settings. 
  * `#@inject` annotation, allows you to inject other languages in strings. Annotation may be before the string or before the statement containing the string.
* IDEA extensions
  * Extension point for package processors and set of interfaces to implement custom package processors (like `Mojo::Base` which is `strict`+`v5.10`+`base`)
