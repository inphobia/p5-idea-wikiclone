Because of incremental nature of IDEA lexer and Perl's heavy context dependency, there are few nuances in Perl syntax for Camelcade plugin:
* Avoid too much of Perl's magic. Perl allows you to do a lot of things. And they might work. And sometimes not as intended. So - be straight, strict, simple, obvious and explicit. No code like this:
```
DynaLoader::bootstrap Math::MPFR $VERSION;
```
Perl is ambiguous enough, to add more. Plugin created to develop a product, not for Perl acrobatic.
* If some package is not being parsed correctly (like `Foo::Bar->method` being parsed as `Foo::Bar()->method`, you may explicitly specify that it's a package: `Foo::Bar::->method`. Don't forget report a bug with code example.
* Use `m/PATTERN/` form of match regexp. Implicit form `/PATTERN/` is supported, but not always being parsed correctly. Implicit form of `?PATTERN?` is not supported in any way. Use `m?PATTERN?`.
* `our` variables should be declared at least once. You may refer them later as `$package::var`, but to make re-factoring works properly you must declare them somewhere. 
* Try to avoid using 'fancy' object method calls `method Foo::Bar`. Use canonical `Foo::Bar->method`. Fancy usage is supported, but may be glitchy.
* Camelcade actively using type in variable declaration: `my Foo::Bar $foo_bar_object`. Types helps to resolve methods.