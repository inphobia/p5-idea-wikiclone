Welcome to the Camelcade wiki.

Camelcade is a Perl5 plugin for IntelliJ IDEA. This project been created for making my own work on Perl5 projects easier, so it has some strange (on the first look) features, like embedded Perl5 support. But I'll be glad if it will help someone else.

Perl5 is really syntax-flexible, what can be really convenient in one-line programs, but often unnecessary in large projects. 

I think, It's not possible to create 100% proper Perl5 lexer/parser without 100% repeating Perl5 respective sources, but we can do our best.

To make your life easier in Camelcade, try to avoid ambiguous constructions whenever it's possible and not really expensive. For example, use `m/regex/` syntax instead of just `/regex/`. More strict syntax will improve plugin performance and save you from unnecessary troubles. You may find list of knwon syntax nuances [here](https://github.com/hurricup/Perl5-IDEA/wiki/Known-syntax-issues).
