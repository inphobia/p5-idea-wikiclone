Camelcade supports [Mojolicious](http://mojolicio.us/) templates. At the moment on the very basic level:

* Parsing templates
* Create Mojolicious template file action
* Basic auto-completion of default helpers and tag helpers
* Here-doc injection in perl code with MOJO marker
* Files navigation in include helper (been done not for Mojo, but pretty handy here)
* Code folding
* Automatic close tag insertion on typing (open tag + space)
* Formatter and pre-formatter for perl code
* Mojolicious helpers support: navigation, completion and refactoring. **NB:** helpers should be declared explicitly, `$app->helper($_, sub{}) for @something;` wont work.
* Mojolicious attributes declared with `has` are supported.
* Both helpers and attributes may be [annotated](https://github.com/Camelcade/Perl5-IDEA/wiki/Annotations)
* Configurable templating language

Since [version 2018.3](https://github.com/Camelcade/Perl5-IDEA/releases/tag/2018.3) `Mojolicious` support available via [separate plugin](https://plugins.jetbrains.com/plugin/11336-mojolicious-support).