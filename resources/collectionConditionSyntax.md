# Collection condition syntax

In order to define a collection with the highest possible flexibility, a mathematical-like syntax is used to define a condition.

## Example
[date >= "2018/05/25"] & [date < "2018/12/31"] & [keyword = ("hollidays" | "christmas")] & [rating > 4]

Here the collection is defined by all pictures with rating > 4 and keyword = holidays or christmas, taken between 2018/05/25 (inclusive) and 2018/12/31 (exclusive)

## Syntax
As we can see the syntax is composed of :
- and conditions groups [condition1] & [condition2]
- or condition groups field operator targets where:
    - field is a metadata field (date, rating, keyword, author, ...)
    - operator is one of these operators: < <= = > >=
    - targets is either a single value between quotes (' or "), example: "2018/05/25" or a set of values between braces ans separated with a pipe |, example ("hollidays" | "christmas"). A logial OR applies between values in this case

## Notes
- logical AND (&) and logical OR (|) make easier the reading of the condition but they are ignored: a logical ANd applies between bracket groups and a logical OR applies between brace groups. Then these 2 syntaxes are equivalent:
    - [date >= "2018/05/25"] & [date < "2018/12/31"] & [keyword = ("hollidays" | "christmas")] & [rating > 4]
    - [date >= "2018/05/25"]  [date < "2018/12/31"]  [keyword = ("hollidays"  "christmas")]  [rating > 4]

- whitespace are ignored
- dates have format YYYY/MM/DD
