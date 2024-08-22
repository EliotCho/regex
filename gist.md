# Regex - gist

Introductory paragraph (replace this with your text)

## Summary

Regex being used

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Typical email address such as `example123@email.com`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Valid Matches](#valid-matches)
- [Invalid Matches](#invalid-matches)

## Regex Components

### Anchors

- `^` asserts the start of the string.
- `$` asserts the end of the string.

### Quantifiers

- `+` matches one or more occurrences of the preceding token.
- `{2,6}` specifies that the preceding token (a character class) must repeat between 2 and 6 times.

### Grouping Constructs

- Parentheses `()` are used to group parts of the pattern. This regex has three groups:
  1. `([a-z0-9_\.-]+)` matches the username part.
  2. `([\da-z\.-]+)` matches the domain name.
  3. `([a-z\.]{2,6})` matches the top-level domain (like `.com` or `.net`).

### Bracket Expressions

- `[a-z0-9_\.-]` matches any lowercase letter, digit, underscore, dot, or hyphen in the username.
- `[\da-z\.-]` matches digits, lowercase letters, dots, or hyphens in the domain.

### Character Classes

- `\d` matches any digit, equivalent to `[0-9]`.

### The OR Operator

- The OR operator (`|`) is not explicitly used in this regex, but alternatives are implicitly defined through character classes.

### Flags

- No flags (like `i` for case-insensitive matching) are used in this pattern.

### Character Escapes

- `\.` is used to match a literal dot (`.`) instead of its special regex meaning (matching any character).

### Valid Matches:

1. example123@domain.com
2. user.name@sub-domain.org
3. firstname.lastname@company.co
4. username_123@domain-name.net
5. user.name@domain.co.uk

### Invalid Matches:

1. plainaddress (Missing @ and domain)
2. @missingusername.com (Missing username)
3. username@.com (Domain name starts with a dot)
4. username@domain..com (Consecutive dots in the domain)
5. username@domain.c (Top-level domain is only one character long, which is not allowed by this regex)

## Author

[Eliot's Github](https://github.com/EliotCho)
