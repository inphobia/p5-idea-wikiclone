There are some known issues, which currently planned to fix.

## Subs refactoring
You may safely refactor static methods, like `Foo::Bar::method`. Objects methods resolution is still in development and can't be reliably refactored. Plugin may do most of the work for you, but manual checking required.

## Unused subs and vars inspections
If sub or variable can't be resolved because of tricky usage or invocation, it will be annotated as unused. But be careful.

## Large files performance
Editing of files larger than 100kb may be laggy. Situation is going better with every version, but not sure it will be perfect sometime. So recommend to avoid creating huge files.

## Spaces before/after markers in Template Toolkit
Current plugin version is compatible with IDEA 14+ and there is a bug for templating languages, which been fixed in IDEA 15. Spaces being set correctly inside other directives, like IF, but still not set on the file level. This will be fixed after migrating to IDEA 15+