# Regular Expressions Explained

Introductory paragraph (replace this with your text)

## Summary

This is an evaluation of the regular expression used for matching HEX values.

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This regex will search for a HEX value that contains letters a through f and digits 0 through 9, stretching either 6 character spaces or 3. 

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

First anchor: `^` from `/^#`

  The caret signifies a string that begins with the characters following the caret. 
  
  For example, `^Abc` indicates that the string must begin with `Abc`.
  
Second anchor: `$/` from `)$/`

  The dollar sign signifies a string that ends with characters preceding the dollar sign. 
  
  For example, `xYzAb$` indicates that the string must end with `xYzAb`

### Quantifiers
  
First quantifier: `?` from `#?(`

  The question mark is a metacharacter. This metacharacter specifies 0 or 1. In this regex, `#?` means that `#` is optional. It can appear either 0 or 1 time. 
  
Second quantifier: `{}`
  Curly brackets specify the number of characters required for a HEX value to match. In this regex, `{6}` and `{3}` indicate that the HEX value can be either 6 or 3 characters long.

### OR Operator
  
There are three OR operators at play in this HEX regex. 

Two of them are inherent within the regex's bracket expressions. Bracket expressions automatically imply that a matching string can contain a combination of any characters contained within the brackets. 

For example: `[a-f0-9]` means any character in the HEX string can contain any character from a-f OR 0-9.

The OR operator `|` from `}|[` indicates just what the name suggests: the regex can match either `6 characters from a-f or 0-9` OR `3 characters from a-f or 0-9`. 

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

Milo is a dedicated student. His interests are vast, but web development currently holds his attention. If you would like to see any of his code, you can find it at https://github.com/Leucisticboi
