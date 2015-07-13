Because of incremental nature of IDEA lexer and Perl's heavy context dependency, there are few nuances in Perl syntax for Camelcade plugin:
* Avoid too much of Perl's magic. Perl allows you to do a lot of things. And they might work. And sometimes not as intended. So - be straight, strict, simple, obvious and explicit.
* Camelcade is less forgiving than Perl. But nothing critical. For example, you can't write: 
```
push @array, $value, if $some_condition;
```
Perl eats this but Camelcade wouldn't like tailing comma. This is one of the restriction left intentionally to bring some order into the mess.
* You can't use anonymous hash in the beginning of statement. For example:
```
sub somesub{
  {
     key1 => 'val1',
     key2 => 'val2',
  }->{$keyvar};
}
```
Is pretty valid from Perl's perspective. But Camelcade requires something before it (like `return` in this case). 
* If some package is not being parsed correctly (like `Foo::Bar->method` being parsed as `Foo::Bar()->method`, you may explicitly specify that it's a package: `Foo::Bar::->method`. Don't forget report a bug with code example.
* Use `m/PATTERN/` form of match regexp. Implicit form `/PATTERN/` is supported, but not always being parsed correctly. For example, after `grep/map/sort {} ` you MUST use `m//` form. Better to use it all the time. Implicit form of `?PATTERN?` is not supported in any way. Use `m?PATTERN?`.
* Literal usage of `{ } [ ] ( )` symbols in matching part of regexp MUST be escaped. Perl itself allows you to use unescaped braces in some occasions, but this form is DEPRECATED. Camelcade requires escaping. 
* `our` variables should be declared at least once. You may refer them later as `$package::var`, but to make re-factoring works properly you must declare them somewhere. 
* Try to avoid using 'fancy' object method calls `method Foo::Bar`. Use canonical `Foo::Bar->method`. Fancy usage is supported, but may be glitchy.
* If your project contains XS subs, declare them with prototypes in pure Perl. Plugin may find such declarations and has no any access to XS parts.
* Currently only ascii identifiers are supported, you can't use non-ascii symbols in identifiers (TBF).
