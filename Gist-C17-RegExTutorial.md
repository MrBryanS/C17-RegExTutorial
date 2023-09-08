# An exploration of Regular Expressions

In order to better understand Regular Expressions, I am researching and creating an outline of the various components of Regular Expressions.

## Summary

We will use the regex expression shown below that is designed to search for and/or test for valid email addresss.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/i`

Note: use this site to test your regex expressions by pasting the above expression into the search field and clicking on the "Test String" button where you can enter an email string to test the expression against.

[https://regexr.com](https://regexr.com)

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

`^` and `$` are anchor characters in this expression indicating, in this case, the start and end of the string the expression is being tested against.

### Quantifiers

The quantifier `+` requires that one or more of the characters in the preceding string or token must match. The quantifier `{2,6}` requires that the length of the preceding string or token must be between 2 and 6 in length.

### OR Operator

The OR operator `|` is not used in this expression. An example of its use would be `cat|dog` which would match either the string "cat" or the string "dog".

### Character Classes

Character classes are used to indicate the characters that must be present in the string the expression is being tested against. In our expression examples of character classes are `[a-z0-9_\.-]` and `[\da-z\.-]`. The first character class indicates that the string must contain one or more characters that are either a-z, 0-9, an underscore, a period, or a dash. The second character class indicates that the string must contain one or more characters that are either a-z, 0-9, a period, or a dash.

Some other character classes that can be used are shown below:
\d : matches a digit character. Equivalent to [0-9]
\D : matches any non-digit character. Equivalent to [^0-9]
\w : matches any word character (alphanumeric & underscore). Equivalent to [A-Za-z0-9_]
\W : matches any non-word character. Equivalent to [^A-Za-z0-9_]
\s : matches any whitespace character (spaces, tabs, line breaks).
\S : matches any non-whitespace character.
\n : matches a line break.

### Flags

The flag `i` is used in this expression to indicate that the expression is case insensitive as email addresses are not case sensitive. There are other flags that can be used to modify the behavior of the expression. For example, the flag `g` can be used to indicate that the expression should be tested against all possible matches in the string rather than just the first match.

Search result:
g : matches the pattern multiple times.
i : makes the regex case insensitive.
m : enables multi-line mode. ...
u : enables support for unicode.
s : short for single line, it causes the . to also match new line characters

### Grouping and Capturing ()

`([a-z0-9_\.-]+)` and `([\da-z\.-]+)` group expressions we are looking for and indicate, in this case, the characters that must be present in the string the expression is being tested against. Groups are used to capture characters that match the expression. Captured characters can be used in a replacement string if the expression were to be used for search and replace.

### Bracket Expressions: []

Brackets are used to create an expression of characters that must be present in the string to get a match. In our example `[a-z0-9_\.-]` and `[\da-z\.-]` are bracket expressions used to indicate the characters that must be present in the string the expression is being tested against. The first expression indicates that the string must contain one or more characters that are either a-z, 0-9, an underscore, a period, or a dash. The second expression indicates that the string must contain one or more characters that are either a-z, 0-9, a period, or a dash.

Note that we are using a flag `i` to indicate that the expression is case insensitive so that the characters A-Z are also included in the expression. Otherwise we'd need to include A-Z in the bracket expression.

### Greedy and Lazy Match

Greedy matching looks for all possible matches in the string. Lazy matching looks for the first match in the string. In our example, the expression is greedy because it is looking for all possible matches in the string.

Greedy matching is the default behavior of the regex engine. To make the expression lazy, we would add a `?` after the quantifier. For example, `+?` would make the expression lazy.

### Boundaries

Boudaries are used to indicate the start and end of a word. We are not using a boundary in our example expression. An example of a boundary would be `\bdog\b` which would match the word "dog" but not the word "dogmatic".

### Back-references

With back-references, a matched substring can be recalled later in the expression. For example, in this expression: `<([A-Z][A-Z0-9]*)\b[^>]*>.*?</\1>` the `\1` at the end of the expression refers 'back' to the first group of characters in the expression: `([A-Z][A-Z0-9]*)`

### Look-ahead and Look-behind

Look-ahead and look-behind are used to match a string that is followed or preceded by another string. An example of a positive lookahead is: `q(?=u)` which would match the "q" in "quiet" but not the "q" in "qat". An example of a negative lookahead is: `q(?!u)` which would match the "q" in "qat" but not the "q" in "quiet".

## Author

This reivew of Regular Expressions was created by Bryan Stauning. You can find me on GitHub at [https://github.com/MrBryanS](https://github.com/MrBryanS)
