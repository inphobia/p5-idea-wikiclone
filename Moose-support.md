Basic [Moose](http://search.cpan.org/~ether/Moose/lib/Moose.pm) support implemented:

* Proper `use Moose;` and `use Moo;` processing.
* `extends` and `with` statements support.
* `inner` and `super` calls resolution.
* Resolution and refactoring in method modifiers: `around`, `after`, `before` and `augment`.
* Parsing, resolution and refactoring for `override` statement ([annotations](https://github.com/Camelcade/Perl5-IDEA/wiki/Annotations) supported).
* Parsing, resolution and refactoring for `has` statement ([annotations](https://github.com/Camelcade/Perl5-IDEA/wiki/Annotations) supported).
* Live-templates for Moose constructions