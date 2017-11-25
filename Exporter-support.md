Camelcade has [`Exporter`](http://perldoc.perl.org/Exporter.html) support:

* auto-completion, resolution and refactoring of imported subs
* auto-completion of exported subs in import statement
* auto-completion, navigation and re-factoring of `@EXPORTER` and `@EXPORTER_OK` arrays
* Unresolved subs inpseciton checks that subs in Exporter's arrays are defined

Please, note, that plugin understands only direct assignment to export arrays:
```perl
@EXPORT = qw/sub1 sub2 sub3/; # this is ok and understandable

# these are not understandable by plugin yet:
my @arr = qw/sub1 sub2/;
@EXPORTER = @arr;

# or
push @EXPORTER, 'sub1';
```