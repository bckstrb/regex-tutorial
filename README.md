# regex-tutorial

Regular expressions (or regex for short) are a sequence of characters used to search and validate text. 

## Summary

In this tutorial, we will be discussing the "matching an email" regex which looks like this: 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This regex would be used to verify that a user has provided a valid email with an "@" and ".[ending]". 

## Table of Contents

- [regex-tutorial](#regex-tutorial)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [Grouping Constructs](#grouping-constructs)
    - [Bracket Expressions](#bracket-expressions)
    - [Character Classes](#character-classes)
    - [The OR Operator](#the-or-operator)
    - [Flags](#flags)
    - [Character Escapes](#character-escapes)
    - [Author](#author)

## Regex Components

### Anchors

Anchors are used to denote the beginning and end of the regex. In our email matching example, the `^` denotes the beginning of the express and the `$` denotes the end of it. 

### Quantifiers

Quantifiers indicate the number of characters that must be found to create a match. If we look at the first subexpression `([a-z0-9_\.-]+)`, the `+` tells us that lower case letters a-z, numbers 0-9, underscore `_`, dot `.`(which uses a backslash `\` to distinguish that is not part of the expression), and hyphen `-` can all apprear at least once.  

### Grouping Constructs

Grouping constructs break down the expression into subexpressions. When we look at our email example `([a-z0-9_\.-]+)` is the first subexpression. This must be true before we can move to the second subexpression `([\da-z\.-]+)`. This must also be true before moving the third and final subexpression `([a-z\.]{2,6})`.

### Bracket Expressions

Brackets indicate a set of characters to be matched using a hypen to define a set. If we look at our first subexpression `([a-z0-9_\.-]+)`, `a-z` does not mean `a` and/or `z` but rather a through z. 

### Character Classes

Character classes match any characters from a given character set. The second subexpression `([\da-z\.-]+)` in our email matching regex, the character class `\d` corresponds to any digit used. 

### The OR Operator

The OR operator `|` is used to match characters or expressions to either the right or left of the operator. Our email matching regex does not use this. 

### Flags

Flags are optional parameters that can be added to a regex to modify its behavior of searching. Our email matching regex does not use this either. Javascript regex uses 6 flags which are as follows: 

    - `i` which will make the regex case insensitive
    - `g` which will make the regex search for all occurances
    - `s` which will make the character `.` match new lines 
    - `m` which will make the boundary characters `^` and `$` match the beginning and ending of every single line instead of the beginning and ending of the whole string
    - `y` which will make the regex start its searching from the index specified
    - `u` which will make the regex assume individual characters as code points rather than code units

### Character Escapes

Character escapes are used to match characters that have a specific meaning in regex. In the first subexpression `([a-z0-9_\.-]+)` in our email matching regex, we are looking for all lower case letters, all digits, and characters underscore `_`, dot `.`, and hyphen `-`. However dot and hyphen have a specific use within the a regex (`[a-z]` is used to represent a through z) therefore the escape `\` is used before the characters to indicate a literal "." and "-". 

### Author

This tutorial was created by Beck Straub.

[Github](https://github.com/bckstrb)

[LinkedIn](https://www.linkedin.com/in/beck-straub-ba8ba123a/)

[Email](mailto:rbccstrb@gmail.com)