Basic [Moose](http://search.cpan.org/~ether/Moose/lib/Moose.pm) support implemented:

* Proper `use Moose;` and `use Moo;` processing.
* `extends` and `with` statements support.
* `inner` and `super` calls resolution.
* Resolution and refactoring in method modifiers: `around`, `after`, `before` and `augment`.
* Parsing, resolution and refactoring for `override` statement (some annotations works).
* Parsing, resolution and refactoring for `has` statement (some annotations works).
* Live-templates for Moose constructions