# Highlight

Written by Dave Goodell <davidjgoodell@gmail.com>

Forked and modified by Scott Baker <scott.baker@gmail.com>

---

### Usage:

```
highlight <PATTERN0> [PATTERN1...]

highlight [--filter COLOR,PATTERN] [--filter COLOR,PATTERN] ...
```

This program takes text via STDIN and outputs it with the given
[patterns](https://perldoc.perl.org/perlre.html) highlighted with various colors.  If no color option
is specified, it defaults to a pre-selected array of colors.

Passing `--case_sensitive` will enable case-sensitive matching. Otherwise
Vim style smartcase matching will be implemented.

If your pattern begins with a dash, you can pass a `--` argument
after any options and before your pattern to distinguish it from an
option.

### Notes:
This package also includes a bonus script `bleach_text` to strip out
ANSI color escape sequences.  The highlight program unconditionally
colors text, regardless of whether STDOUT is connected to a terminal or
not, so such a program is occasionally useful.

### Colors:

Filters can be assigned a **specific** color by using the ANSI number available in the `term-colors.pl` script.

### Examples:
```
cat README.md | highlight colors? by 'pattern[\ds]?' text program with '\bhighlight\b'

cat nagios.log | highlight --filter '11,\bWARNING\b' --filter '82,\bOK\b' --filter '196,\bCRITICAL\b'
```
