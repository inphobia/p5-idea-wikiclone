There are some known issues, which currently planned to fix.

##Subs refactoring
You may safely refactor static methods, like `Foo::Bar::method`. Objects methods resolution is still in development and can't be reliably refactored. Plugin may do most of the work for you, but manual checking required.

##Unused subs and vars inspections
If sub or variable can't be resolved because of tricky usage or invocation, it will be annotated as unused. But be careful.

##Large files performance
Editing of files larger than 100kb may be laggy. Problem is still not localized.
