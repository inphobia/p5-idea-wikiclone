Here is the list of features, currently implemented in the Camelcade:

* Perl5 lexing and parsing. As soon as it's not a port of native Perl5 lexer/parser, it may have some bugs. If you've encountered situation, where your code is not being parsed properly, feel free to create an issue with code example. 
  * Currently supported languages are Perl5, POD and php-style Perl5 (Embedded perl)
* Perl5 interpreter (SDK) and Perl5 module type support. You should add Perl5 interpreter as project SDK to give Camelcade access to installed packages. Library paths should be detected automatically and added to the classpaths.
  * If your project has it's own lib directory, you should add it as a Library in `File->Project structure->Modules->Your module->Dependencies`. All package names in use/require being resolved relatively to such library paths.
* Syntax highlighting. Perl and POD sources are highlighted and there is a Default theme, taken from NP++. There is no Darcula theme in the plugin jar.
  * Color settings dialog example is still buggy and doesn't show some syntax constructions (TBF).
* Brace matching, code folding, quote handling, live templates for Perl5.
* Create Perl5 file context menu action.
* Lexical and global variables auto-completion, navigation and refactoring.
* Packages auto-completion, navigation and refactoring.
* Subs auto-completion, navigation and refactoring are only partially implemented. See current subs resolution status.
* Heredoc markers navigation refactoring.
* Subs annotations (see below)
* Basic code inspections: 
  * Packages
    * Missing package file
    * Undefined namespace
    * Multiple namespace definitions
    * Namespace clash with core namespace
  * Subs
    * Deprecated sub
    * Undefined and undeclared sub 
    * Multiple sub definitions/declarations
  * Variables
    * Undeclared variable
    * Shadowing
    * Lexical built-in declaration
* IntelliLang integration. Heredoc texts may be automatically injected with other language, depending on marker text. To make this work, IntelliLang plugin must be enabled and appropriate Language supported by IDEA natively or via plugin. Following markers are currently supported:
  * JavaScript: JS, JS15, JS16, JS17, JS18, APPLEJS
  * Database: SQL, MYSQL, PGSQL, TSQL, OSQLP, DB2, SQL92, SQLITE, SYBASE, HSQLDB, GSQL, OSQL (Both Database navigator and JetBrains Database tools are supported)
  * Web-related: JSON, CSS, DTD, XHTML, XML, HTML
  * Misc: JAVA, YAML, MANIFEST, PHP, PYTHON

## Annotations
Camelcade supports subs annotaions, which can help you to maintain your code and help Camelcade to resolve subs properly. Syntax is following:

```
#@deprecated
sub some_deprecated_sub
{
...
}
```
Such sub will be stroke out everywhere in your project sources.

Following annotations are implemented: `deprecated, returns, method and override`. Currently, only `deprecated` does something.