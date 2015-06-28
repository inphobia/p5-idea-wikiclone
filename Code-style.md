To make your life easier in Camelcade, try to avoid ambiguous constructions whenever it's possible and not really expensive:

* use `m/regex/` syntax instead of just `/regex/`
* use parentheses for filehandle reading `(<FH>)`
* avoid creating top-level namespaces
* avoid creating lowercase namespaces
* avoid creating `Foo::bar` package and `sub Foo::bar` in the same time.

More strict syntax will improve plugin performance and save you from unnecessary problems. You may find list of knwon syntax nuances [here](https://github.com/hurricup/Perl5-IDEA/wiki/Camelcade-Perl-syntax-nuances).
