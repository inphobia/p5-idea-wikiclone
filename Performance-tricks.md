Unlike editors, the IDE provides much more features and tools and does a lot of different things aside of parsing and highlighting. Because of this IDE is always slower than simple editor. Everything costs something.

Perl5 plugin was written by a perl fan, not a professional language plugins developer, so it's far from perfect. This fact causes more performance setbacks.

Some of performance issues are fixable and they will be, in time. With every version, plugin becomes faster and faster. Others, however, caused by IDEA architecture and can't be fixed by plugin author, but may be changed by JetBrains, again, in time.

However, there are some performance tricks you could use to make your work more comfortable. 

#Multiple namespaces in one file
<b>Don't use multiple namespaces in one file</b>

I think it's bad practice to put multiple namespaces into the one file and the only reason this is reasonable - using closures. But this is twice bad :) 

Howewer, if by some reasons need to use multiple namespaces, use braced format, it works much faster in Camelcade:
```
package Foo::Bar{
    ...
}
package Foo::Baz{
    ...
}
...
package Foo::Foo{
    ...
}
```
instead of
```
package Foo::Bar;
    ...
package Foo::Baz;
    ...
package Foo::Foo;
    ...
```
This problem caused by the plugin and probably going to be fixed.

#Identifiers
<b>Use long and self-explanatory variables and subs names if it's possible. `get_something_this` and `$database_handler` is much faster than `gst` and `$dbh`</b>

I guess that thre are two reasons of short perl identifiers:

1. Historical. Perl has been created as admin command tool, not a common programming language.
2. For a long time Perl has not any IDE and therefore - autocompletion.

Basically, when IDEA needs to find usages of a variable/sub, it takes all same words from internal index and checks every found word, if it leads to this definition. And this being done not only when you explicitly trying to find usages. IDEA may do this for it's internal reasons.

#Large files
<b>Avoid using large files, keep your programs modular</b>

This is the problem of plugin's parser. IDEA requires separate lexer and perser, so it's not possible to port native perl parser for it (perl parser and lexer works together). The easiest way was to use simple lexer and BNF with manual tunings for parser. As a result - we have a descending perl parser.

Aside of parser, plugin has a lot of minor performance setbacks, that being fixed with every next version. 

Large file is really situational and depends on your hardware, but I found comfortable to work with few thousands lines of code.
