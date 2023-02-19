# Turorial for using RegEx to match an email

    This tutorial will explain how to format a RegEx (regular expression) to find an email, this type of expression can be used for many different situations where you need to find something that matches your search parameters. For this tutorial we will be using an email address as the example, but with small changes to the formating of the RegEx you can search for any number of things (i.e. usernames, password strength validation, URL, dates, ect.). It is also important to take note that our RegEx will not work for every email address, as we do not allow special characters, only alphanumeric values, but this could be simply changed if special characters are required.

## Summary

    The RegEx we will be using today is an email checker to validate email addresses, the syntax this RegEx will follow is /^[a-zA-Z0-9+_.-]+@[a-zA-Z0-9.-]\.[a-zA-Z0-9]+$/ . It is important to remember that RegEx is consdiered a literal, so we use forward slashes in place of quotations.

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
    The ^ and $ are consdidered anchors and signify the beginning and end of the string respecively. It is important to note that putting ^ inside of the brackets [] will turn the validation to a negative validation (ie [^0-9] would look for a string that does not include numbers).

### Quantifiers
    RegEx quantifiers are put within curly brackets {}, we did not use quantifiers in this particular example since email address lengths can vary greatly, but if we wanted to make sure the length of the domain was between 5-9 characters long we could write the expression as /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]{5,9}\.[a-zA-Z0-9]$/ if we wanted to put a specific length on the email address we would put the qualifier after the first set of brackets [] and before the @ symbol. Other options for quantifiers exist as well being *, +, and ?, we will not be using those for this tutorial but it is important to know that they may be used as well as to not be confused if they come up in a RegEx you see in your coding journey.

### Grouping Constructs
    Grouping constructs have two primary categories, capturing and non capturing. Capturing groups capture the matched character sequence for possibly re-use, non capturing does not a grouping construct ca be made non capturing by adding ?: at the beginnign of the expression made within parenthesis (). As your RegEx grows more complicated you may want to check multiple sections of the string, for this you will use parenthesis () each section within a parenthesis is known as a subexpression, unlike bracket expressions subexpressions look for exact matches rather than certain characters unless told otherwise. 

### Bracket Expressions
    Bracket expressions represent a range of characters that the RegEx will search for, anything inside of brackets [] will be considered a bracket expression, this can include a string of letters, numbers or special characters (ie [abc], [abcdef], [456789], ect). More commonly though you will see a hyphon inbetween letters or numbers like we have in our example, checking for any lowercase letters from a to z [a-z], uppercase letters from A to Z [A-Z], and any number between 0 and 9 [0-9], bracket expressions may also contain special characters we used a hyphon, underscore and period in ours, but you could add as many as you like. Bracket expressions do not require all special characters, letters, or numbers, they jsut check for any within the search range.

### Character Classes
    Character classes within a RegEx operator define a set of characters, any one of which may occur within the input string, bracket expressions can be considered character classes, but we have a few others to cover as well. Such as a period . which will match any character except for the newline escape character (\n), or a backslash d (\d) which will match any arabic numeral digit (which is the numerals we use in the english language, and other latin based languages), as well as backslash w (\w) which will match any latin based alphanumeric character including an underscore (_), or backslash s (\s) which will match any single whitespace character including tabs and linebreaks. Any of these can be inversed by capitolizing the letter, which is similar to our negative validation, searching for the opposite of what its established job is.

### The OR Operator
    A bracket expression does not require all patterns to be met by the string, we may want to use that logic when looking at a subexpression as well, that is a use case for the OR operator (|) a straight vertical line signifies or in JavaScript in general and it is not different in a RegEx expression, so if we wanted a subexpression to search for 1, 2, or 3 we would write the expression as (1|2|3) rather than as (123).

### Flags
    In the summary of this tutorial we stated that RegEx are considered literals so they must begin and end with a / but there is an exception to that rule, and that exception is what is known as flags. All flags are a single letter, they can be used after the final slash to add parameters to the search, there are six flags and they can be used in conjuction with each other. The flags and there use cases are as follows

    i   this flag is to signify case insesitivity, with this flag you do not need to specifiy both capital and lowercase letters.

    g    this flag is to singify all matches, without it only the first match will be returned.

    m   this flag is to singify that multiple lines of input should be treated as multiple lines.

    s   this flag is enables "dotall" mode, which allows a period to match a newline character (\n).

    u   this flag is used to enable full Unicode mode, this flag enables correct processing of surrogate pairs.

    y   this flag enables "Sticky" mode, searching at the exact position in the text.

        these are just brief explanations of each flag, more research will most likely be needed to use these flags properly.

### Character Escapes

    The backslash (\) is the RegEx escape character, it can be used to escape a character that would otherwise be interperted literally, for example when creating a quantifiers, bracket expressions or subexpressions you would use the {} [] or () respectively, but if you want to search for the parenthesis itself in a string you can add the backslash before the parenthesis. However when inside of a bracket expression, the backslash and all other special characters lose their special signifigance.

## Author

    This was written by Kai Ropp, a UW fullcamp bootstack student who recently began his coding journey, a longtime fan of tech but recent tech creater. Kai is a Pacific Northwest local who has lived in Seattle and it's surrounding area for most of his life. 
        below is a link to his github account to find his other projects.
            https://github.com/kairo97
