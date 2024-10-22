**Regular expressions** _\(regular expressions, regex\)_ are a formal language for searching and replacing substrings in text. With the help of regex, you can define a pattern and find or replace pieces of the text that match it. Many text editors such as Notepad++, Sublime, Geany, Atom etc., support regular expressions. 

Websites:

* [**http://regexr.com/**](http://regexr.com/)
* [**https://regex101.com/**](https://regex101.com/)

When working with the website, you will not only see matches but also the breakdown of your regular expression.

This is how working with regular expressions looks in Notepad++ \(to access this menu, press Ctrl+F or Search\) and set the necessary checkboxes \(be sure to enable regular expressions, and if necessary, case sensitivity, search direction, and line wrap consideration\).

### Selecting and Grouping Symbols

* **.** - any character
* **\|** - _either_ everything on the left, _or_ what's on the right
* **\(\)** - grouping of characters \(if in doubt about whether to use them, it's better to use them :\) 

![](./assets/regex1.png)

The part of the regex enclosed in parentheses is called a **group**. Groups are numbered by the opening parenthesis.

* **\1** - group with the corresponding number \(used in replacement\)
* **\[ \]** - any single character from those enclosed in brackets
* **\[^ \]** - any single character except those enclosed in brackets

![](./assets/r7.png)

### Quantitative Operators (Quantifiers)

* **?** - the previous character/group may or may not be present
* **+** - the previous character/group may repeat 1 or more times
* **\*** - the previous character/group may repeat 0 or more times
* **{n,m}** - the previous character/group may repeat from n to m times, inclusive
* **{n,}** - the previous character/group in parentheses may repeat n or more times
* **{,m}** - the previous character/group may repeat up to m times
* **{n}** - the previous character/group repeats n times

### Symbol Classes (Ranges)

* **\[A-Z\]** - _any one_ uppercase character \(Latin alphabet\)
* **\[a-z\]** - any lowercase character \(Latin alphabet\)
* **\[А-Я\]** - any uppercase character \(Cyrillic alphabet\)
* **\[а-я\]** - any lowercase character \(Cyrillic alphabet\)
* **\[0-9\]** or **\d** - a digit
* **\[^0-9\]** or **\D** - any character except a digit

You can combine them:

* **\[A-Za-z\]** - any uppercase or lowercase character \(Latin alphabet\)
* **\[A-Za-z0-9\]** - any uppercase or lowercase character \(Latin alphabet\) and digits
* **\[A-Za-z0-9\_\]** or **\w** - any uppercase or lowercase character \(Latin alphabet\), digits, and _
* **\[^A-Za-z0-9\_\]** or **\W** - anything except uppercase or lowercase characters \(Latin alphabet\), digits, and _

#### Special characters

* **\t** - tab
* **\s** - any whitespace character
* **\S** - anything except spaces
* **\n** \(or **\r\n** on Windows\) - new line
* **^** - start of the line
* **$** - end of the line

### "Greedy" and "Lazy" Operators

Quantifiers by default behave greedily: this means that they try to "consume" as many characters as possible and, out of all possible options, they will catch the longest string. 

| Greedy Quantifiers   | Lazy Quantifiers   |
| :---                 | :---               |
| \*                   | \*?                |
| +                    | +?                 |
| ?                    | ??                 |
| {min, max}           | {min, max}?        |


### Escaping Special Characters

As you've already noticed, like any language, regular expressions are written using a special alphabet—dots, asterisks, parentheses, etc. But what if you need to find special characters like + or \* in the text? It's simple: you need to **escape** them by placing a backslash \ (backslash) before them. In this example, we escape \* to make it a literal text character, while + remains a special character and means "one or more times".

### Backreferences
