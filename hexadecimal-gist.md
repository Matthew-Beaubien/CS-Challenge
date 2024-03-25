# Hexadecimal Colour Code Validation Regex

This literature will be exploring the hexadecimal colour code validation regex. It will be broken down and explained in detail in order to create a comprehensive guide that is easily understandable.

## Summary

Hexadecimal colour codes are used to specify colours in web development. They typically start with a hash symbol (#) and then either 3 or 6 hexadecimal digits which refers to the intensity or red, green, and blue. Each pair of digits coresponds to the intensity of each colour which ranges from "OO", which is the lowest intensity, to "FF", which is the highest intensity.

Regex example: /^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$/

Code example: 

function isValidHexColor(color) {
    const pattern = /^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$/;
    return pattern.test(color);
}

// Test the function
const colors = [
    "#FF0000", // Valid: red
    "#00FF00", // Valid: green
    "#0000FF", // Valid: blue
    "#FFFFFF", // Valid: white
    "#000",    // Valid: black (shortened)
    "#FFF",    // Valid: white (shortened)
    "#GHIJKL", // Invalid: contains non-hex characters
    "#12345",  // Invalid: too few digits
    "#1234567" // Invalid: too many digits
];

colors.forEach(color => {
    console.log(`${color}: ${isValidHexColor(color)}`);
});

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

The regex pattern (`/^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$/`) is made up of several components: 

[^] and [$] : Anchors.
[#?] : Looks for the optional hash symbol at the start of the string. 
[ ([a-fA-F0-9]{6}|[a-fA-F0-9]{3}) ] : Two alternatives grouped within parentheses. Either six characters [ {6} ] or three characters [ {3} ] that are hexadecimal digits [ [a-fA-F0-9] ].

### Anchors

^ and $

These are the ANCHORS. They signal the begining and the end of the string. This ensures that the entire string matches the regex pattern.

### Quantifiers

{6} and {3} 

The QUANTIFIERS indentify the exact number of hexadecimal characters to match in the pattern. {6} matches exactly six characters, and {3} matches exactly three characters.

### Grouping Constructs

([a-fA-F0-9]{6}|[a-fA-F0-9]{3})

The grouping construct for the regex groups the two alternatives of six or three characters and is separated by the OR operator (|). This construct allows for the matching of either six or three hexadecimal characters.

### Bracket Expressions

[a-fA-F0-9]

This is a bracket expreesion which holds a character class, matching any character that is a lowercase letter (a-f), uppercase letter (A-F), or digit (0-9). This ensures that only valid hexadecimal characters are matched.

### Character Classes

[a-fA-F0-9]

As stated above, within the brackets is the character class which matches any character that is a lowercase letter (a-f), uppercase letter (A-F), or digit (0-9).

### The OR Operator

| 

The OR operator allows for identifying multiple alternatives within a regex pattern. In this case, it separates two alternatives for matching either six or three hexadecimal characters.

### Flags

In this specific regex pattern, there are no flags used.

### Character Escapes

In this regex pattern, there are no character escapes.

## Author

This guide was written by Matt B, a web developer located in Toronto, Ontario. 

https://github.com/Matthew-Beaubien

