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
  
  For example, `xYzAb$` indicates that the string must end with `xYzAb`.

  In the case of our HEX regex, this anchor indicates that our matching string must be either 6 or 3 characters in length.

### Quantifiers
  
First quantifier: `?` from `#?(`

  The question mark is a metacharacter. This metacharacter specifies 0 or 1. In this regex, `#?` means that `#` is optional. It can appear either 0 or 1 time. 
  
Second quantifier: `{}`
  Curly brackets specify the number of characters required for a HEX value to match. In this regex, `{6}` and `{3}` indicate that the HEX value can be either 6 or 3 characters long.

### OR Operator
  
There are three OR operators at play in this HEX regex. 

Two of them are inherent within the regex's bracket expressions. Bracket expressions automatically imply that a matching string can contain a combination of any characters contained within the brackets. 

For example: `[a-f0-9]` means any character in the HEX string can contain any character from a-f OR 0-9.

The OR operator pipe symbol `|` from `}|[` indicates just what the name suggests: the regex can match either `6 characters from a-f or 0-9` OR `3 characters from a-f or 0-9`. 

### Character Classes

First character class: `a-f` from `[a-f0-9]`
  
  This character class indicates that each character in the HEX value may be any lowercase letter from `a to f`. 

  Example: `abcdef`, `bbbbbb`, or `caefdd` will match. `efghad` will not match because it contains letters outside of the set range. `aBcDef` also does not match due to multiple uppercase characters.

Second character class: `0-9` from `[a-f0-9]`

  This character class indicates that each character in the HEX value may also be any number from `0 to 9`. 

  Example: `000000`, `123456`, or `480658` will match this character class. 

Since both character classes are combined in our [bracket expression](#bracket-expressions), any characters from `a-f` or `0-9` will match. We do not *have* to use both numbers *and* letters in order to match.

### Flags

Our HEX regex does not contain any flags; however, I'll still include a couple of regex flag examples.

  `d` generates indices for substring matches.

  `m` allows `^` and `$` to match newline characters.

### Grouping and Capturing

`([a-f0-9]{6}|[a-f0-9]{3})` is a capturing group. This group is enclosed in parentheses and consists of two alternatives separated by the `|` pipe symbol which we identified previously in [Or Operator](#or-operator). 

  `[a-f0-9]{6}` is the first alternative, and it captures a 6-character hexadecimal color code. It matches exactly 6 hexadecimal digits (0-9 or a-f).

  `[a-f0-9]{3}` is the second alternative, and it captures a 3-character hexadecimal color code. It matches exactly 3 hexadecimal digits (0-9 or a-f).

### Bracket Expressions

`[a-f0-9]` is repeated twice in the hexadecimal regex. Once before the OR operator, and once after. As stated in [Character Classes](#character-classes), this bracket expression matches a single character that is a hexadecimal digit. It includes the characters `a-f` and digits `0-9`.

The quantifiers `{6}` and `{3}` determine how many times the preceding bracket expression should be matched within the HEX string.

### Greedy and Lazy Match

**Greedy Matching** 

`Greedy quantifiers` attempt to match as much text as possible while still allowing the overall regex to match. In this case, the `{6}` and `{3}` quantifiers are greedy. When applied to the regex, the capturing group will attempt to capture as many characters as possible while ensuring the entire regex matches.

  Example: If the full string is `#aabbccdd`, the greedy quantifier `{6}` would capture `aabbcc`, the maximum it can match, rather than `aabb` or `aabbccdd`.

### Boundaries

The HEX regex boundaries are established by the `^` and `$` anchors. The caret symbol represents the start-of-line anchor while the dollar symbol represents the end-of-line anchor. It ensures that the input string must start with an optional `#` (the start) and end with a valid 6-character or 3-character hexadecimal color code (the end) with no extra characters before or after.

### Back-references

The HEX regex does not contain any back-references. Back references are used to refer to capturing groups within the regex, allowing you to match the same text that was previously captured by a capturing group. In our regex there are capturing groups, but they are not being referenced elsewhere in the pattern.

### Look-ahead and Look-behind

The HEX regex does not contain any **lookahead or lookbehind assertions**. 

  A `positive lookahead` checks if something *comes after* a specific point in the string, but *it doesn't include that something* in the match.

  A `negative lookahead` checks for the *absence* of something *after* a specific point in the string.

  A `positive lookbehind` checks if something *comes before* a specific point in the string, but *it doesn't include that something* in the match.

  A `negative lookbehind` checks for the *absence* of something *before* a specific point in the string.

## Author

Milo is a dedicated student and explorer. His interests are vast, but web development currently holds his attention. If you would like to see any of his code, you can find it at https://github.com/Leucisticboi
