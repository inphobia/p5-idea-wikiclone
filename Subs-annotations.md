Camelcade introduces subs annotaions, which can help you to maintain your code and help Camelcade to resolve subs properly. Syntax is following:

```
#@deprecated
sub some_deprecated_sub
{
...
}
```
Such sub will be stroke out everywhere in your project sources.

Following annotations are implemented: `deprecated, returns, method and override`. Currently, only `deprecated` does anything.