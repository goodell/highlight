[![Travis CI build status](https://travis-ci.org/goodell/highlight.svg?branch=master)](https://travis-ci.org/goodell/highlight)

Written by Dave Goodell <davidjgoodell@gmail.com>
MIT License (see "highlight" script)

The latest version should be available at github:

  http://github.com/goodell/highlight

This package also includes a bonus script (`bleach_text`) to strip out
ANSI color escape sequences.  The highlight program unconditionally
colors text, regardless of whether `STDOUT` is connected to a terminal or
not, so such a program is occasionally useful.

------------------------------------------------------------------------

```
Usage: ./highlight [-i] [--color=COLOR_STRING] [--] <PATTERN0> [PATTERN1...]
  or
Usage: ./highlight [-i] [--filter COLOR,PATTERN] [--filter COLOR,PATTERN]

This is highlight version 1.2.

This program takes text via standard input and outputs it with the given
perlre(1) pattern(s) highlighted with the given color.  If no color option
is specified, it defaults to 'bold red'.  Colors may be anything
that Perl's Term::ANSIColor understands.  This program is similar to
"grep --color PATTERN" except both matching and non-matching lines are
printed.

The default color can be selected via the $HIGHLIGHT_COLOR environment
variable.  The command-line option takes precedence.

Passing -i or --ignore-case will enable case-insensitive matching.

If your pattern begins with a dash ('-'), you can pass a '--' argument
after any options and before your pattern to distinguish it from an
option.
```
