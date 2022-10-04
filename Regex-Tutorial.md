# Regex Tutorial - Matching an Email

Regular expressions (shortened as "regex") are special strings representing a pattern to be matched in a search operation. They are an important tool in a wide variety of computing applications, from programming languages like Java and Perl, to text processing tools like grep, sed, and the text editor vim.

## Summary

This tutorial will focus on explain the regex that used to match emails.

- `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

We will give breakdown for the regex above.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors are a different breed. They do not match any character at all. Instead, they match a position before, after, or between characters
<br/>
<br/>
For the regex we have above:

- `^` asserts position at start of the string
- `$` asserts position at the end of the string, or before the line terminator right at the end of the string (if any)

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.
<br/>
The `+` quantifier matches the preceding element one or more times.
<br/>
The `{n,m}` quantifier matches the preceding element at least `n` times, but no more than `m` times, where `n` and `m` are integers.
<br/>
<br/>
For the regex we have above:

- the `+` operator acts as the qualifier which will look for one or more instances of everything in brackets
- the `{2,6}` acts as a qualifier, which matches between 2 and 6 characters from a to z

### Grouping Constructs

Grouping constructs delineate the subexpressions of a regular expression and capture the substrings of an input string.
<br/>
<br/>
For the regex we have above:

- The first subgroup is `([a-z0-9_\.-]+)` which matches the email username
- The second subgroup is `([\da-z\.-]+`) which matches the domain name or mail server
- The last subgroup, `([a-z\.]{2,6})`, captures the top-level domain, such as .com or .org

### Bracket Expressions

Bracket expressions are a list of characters and/or character classes enclosed in brackets []. Use bracket expressions to match single characters in a list, or a range of characters in a list. If the first character of the list is the carat ^ then it matches characters that are not in the list.
<br/>
<br/>
For the regex we have above:

- For `[a-z0-9_\.-]`, `[a-z]` matches any letters from 'a' to 'z' (case sensitive). `[0-9]` matches any number between '0' to '9'. `[_\.-]` matches the characters "\_", "-", and "."

- For `[\da-z\.-]`, `[\d]` matches any digital character from '0' to '9'. `[a-z]` matches any letters from a to z (case sensitive). `[\.-]` matches the characters "\_", "-", and "."

- For `[a-z\.]`, this is looking for any character between "a" to "z" and "."

### Character Classes

A character class matches any symbol from a certain character set.Simply place the characters you want to match between square brackets. If you want to match an a or an e, use `[ae]`. You could use this in gr`[ae]`y to match either gray or grey.

### The OR Operator

You can use the `|` operator (logical OR) to match characters or expression of either the left or right of the `|` operator. For example the `(t|T)` will match either t or T from the input string.

### Flags

A flag is an optional parameter to a regex that modifies its behavior of searching. A flag changes the default searching behavior of a regular expression. It makes a regex search in a different way. A flag is denoted using a single lowercase alphabetic character.

### Character Escapes

To match a character having special meaning in regex, you need to use a escape sequence prefix with a backslash ( `\` ).
<br/>
In order to specifically match a period, you need to escape the dot by using a slash `\.` accordingly
<br/>
<br/>
For the regex we have above:

- `[a-z0-9_\.-]`
- `[\da-z\.-]`
- `[a-z\.]`

## Author

[Allen Yin](https://github.com/Canon70D) - Learning to be a full stack developer
