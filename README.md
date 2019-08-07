# Highlight

Written by Dave Goodell <davidjgoodell@gmail.com>  
Forked and modified by Scott Baker <scott.baker@gmail.com>

---

### Usage:

    highlight <PATTERN0> [PATTERN1...]
    
    highlight [--filter COLOR,PATTERN] [--filter COLOR,PATTERN] ...

This program takes text via standard input and outputs it with the given
[perlre(1)](https://perldoc.perl.org/perlre.html) patterns highlighted with various colors.  If no color option
is specified, it defaults to a pre-selected array of colors. This program is similar to `grep --color PATTERN` except both matching and non-matching
lines are printed.

Passing `--case-sensitive` will enable case-sensitive matching. Otherwise
Vim style smartcase matching will be implemented.

If your pattern begins with a dash ('-'), you can pass a '--' argument
after any options and before your pattern to distinguish it from an
option.

---

### Note: 
This package also includes a bonus script `bleach_text` to strip out
ANSI color escape sequences.  The highlight program unconditionally
colors text, regardless of whether STDOUT is connected to a terminal or
not, so such a program is occasionally useful.
