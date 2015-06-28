Because of incremental nature of IDEA lexer and Perl's heavy context dependency, there are few nuances in Perl syntax for Camelcade plugin:
* After initial project indexing, some package subs calls, like `Foo::bar` may be incorrectly recognized as package names. Hitting enter (causes re-lexing) should solve the problem.
* In constructions like `(grep | map | sort) { ... } (/regex/ | <handle>)` you should help lexer to recognize regex or handle reading. Use `m/regex/` to force regex proper parsing and use enclosing parentheses for filehandle reading: `(<handle>)`
* `our` variables should be declared at least once. You may refer them later as `$package::var`, but to make re-factoring works properly you must declare them somewhere. 
* Try to avoid using 'fancy' method calls `method Foo::Bar`. Use canonical `Foo::Bar->method`. Fancy usage is supported, but may be glitchy.
* If your project contains XS subs, declare them with prototypes in pure Perl. Plugin may find such declarations and has no any access to XS parts.
* Braces symbols in regex MUST be escaped. `/\p{Word}/` is ok, but `/foo{/` is not. Perl recommends to do it but it's not required. Camelcade requires escaping.
* Currently only ascii identifiers are supported, you can't use non-ascii symbols in identifiers.