# Regular Expressions

**Regular expressions** (shortened as **regex** or **regexp**) refer to a formal language for matching and replacing sequences of characters with specific patterns. Many text editors such as Google Docs, Notepad++, Sublime, Geany, Brackets, Atom, etc. support regular expressions. They can be very useful for validating, cleaning, and restructuring text data.

## Turning on regex mode in a text editor

* Ctrl+F — search
* Ctrl+H — replace

### Notepad++

<img src="./img/npp1.png" alt="Search" style="height: 300px; margin-right: 10px;"/>&nbsp;&nbsp;&nbsp;<img src="./img/npp2.png" alt="Replace" style="height: 300px;"/>

### Sublime Text
<img src="./img/sublime1.png" alt="Search" style="height: 350px; margin-right: 10px;"/>&nbsp;&nbsp;&nbsp;<img src="./img/sublime2.png" alt="Replace" style="height: 350px;"/>

Alternatively, you can use https://regex101.com/ or any other online regex tester. These websites are great for learning, because they provide a detailed explanation for every bit of your regular expression.

<img src="./img/regex101.png" alt="Search" style="height: 400px; margin-right: 10px;"/>

## How does a regular expression look like?
A regular expression can be as simple as a single character or word. 

<img src="./img/char.png" style="height: 440px; margin-right: 10px;"/>

<img src="./img/word.png" style="height: 300px; margin-right: 10px;"/>

However, regular expressions more often look like something your cat typed jumping on the keyboard, or just like a wall of brackets. Although they may seem intimidating at first glance, their syntax is actually quite straightforward!

<img src="./img/howto.jpg" alt="How To" style="height: 300px; margin-right: 10px;"/>&nbsp;&nbsp;&nbsp;<img src="./img/brackets.jpg" alt="Brackets" style="height: 300px;"/>

## Regex Syntax

## Symbol ranges

| Syntax   | Description                                    |
|:-----------|:------------------------------------------------|
| **.**     | any single character                           |
| **A\|B**  | match either A (everything on the left) or B (everything on the right)
| **[ABC]**             | any single character from those in brackets           |
| **[^ABC]**            | any single character except those enclosed in brackets     
| **[A-Z]**     | any single uppercase [basic Latin](https://en.wikipedia.org/wiki/Basic_Latin_(Unicode_block)) character        |
| **[a-z]**     | any lowercase character (Latin alphabet)               |
| **[0-9]** or **\d**| a digit                                         |
| **[^0-9]** or **\D**| any character except a digit                    |
 
You can combine ranges:

| Syntax   | Description                                    |
|:-----------|:------------------------------------------------|
| **[A-Za-z]**               | any uppercase or lowercase character from basic Latin alphabet                          |
| **[A-Za-z0-9]**            | any uppercase or lowercase character from basic Latin alphabet, and digits               |
| **[A-Za-z0-9_]** or **\w**| any uppercase or lowercase character from basic Latin alphabet, digits, and _            |
| **[^A-Za-z0-9_]** or **\W**| anything except uppercase or lowercase characters (Latin alphabet), digits, and _ |

**Tip**: regular expressions operate Unicode symbol ranges, and you can create custom ones using [Unicode blocks](https://www.compart.com/en/unicode/block) as reference.

| Syntax   | Description                                    |
|:-----------|:------------------------------------------------|
| **[А-Я]**     | any uppercase character from basic Cyrillic alphabet           |
| **[а-я]**     | any lowercase character from basic Cyrillic alphabet           |
| **[\u1680-\u169c]** | Ogham alphabet |
|**[\u0250-\u02af]**| International Phonetic Alphabet (IPA) |

## Groups and backreferencing

A part of a pattern can be enclosed in parentheses. This is called a **capturing group**. 

| Syntax   | Description                                    |
|:-----------|:------------------------------------------------|
| **( )**                        | capturing group                                                                |
| **(? )**                       | non-capturing (passive) group                                                   |
| **\1**                         | group with the corresponding number     

Groups are numbered by the opening parenthesis.

![](./img/r7.png)

## Quantifiers

| Syntax   | Description                                    |
|:-----------|:------------------------------------------------|
| **?**                          | the previous character/group may or may not be present                         |
| **+**                          | the previous character/group may repeat 1 or more times                        |
| **\***                         | the previous character/group may repeat 0 or more times                        |
| **{N,M}**                      | the previous character/group may repeat from N to M times, inclusive           |
| **{N,}**                       | the previous character/group may repeat N or more times                        |
| **{,M}**                       | the previous character/group may repeat from zero to M times                          |
| **{N}**                        | the previous character/group repeats exactly N times 

### "Greedy" and "lazy" quantifiers

Quantifiers by default behave greedily: this means that they try to "consume" as many characters as possible and, out of all possible options, they will catch the longest string. 

| Greedy Quantifiers   | Lazy Quantifiers   |
| :---                 | :---               |
| \*                   | \*?                |
| +                    | +?                 |
| ?                    | ??                 |
| {min, max}           | {min, max}?        |


## Special characters

| Syntax   | Description                                    |
|:-----------|:------------------------------------------------|
| **\t**                         | tab                                                                            |
| **\r**                         | carriage return                                                                |
| **\n**                         | new line   
| **\s**                         | any whitespace character                                                       |
| **\S**                         | anything except spaces  

### Anchors 

| Syntax   | Description                                    |
|:-----------|:------------------------------------------------|
| **^**                          | start of the line                                                              |
| **$**                          | end of the line    

## Escaping syntax elements

As you've already noticed, like any language, regular expressions are written using a special alphabet—dots, asterisks, parentheses, etc. But what if you need to find special characters like + or \* in the text? It's simple: you need to **escape** them by placing a backslash before them. In this example, we escape \* to make it a literal text character, while + remains a special character and means "one or more times".

## Exercises 

#### Exercise 1
What will the following regex match? What do you have to change to capture phrases "I love regex!" and "I hate regex!"? Make another change for the regex to capture any of these phases with one or more exclamation marks.

```
I love|hate regex!
```
#### Exercise 2
Using [Unicode blocks](https://www.compart.com/en/unicode/block), write a regex to match:

* Devanagari alphabet
* All Georgian characters (main + extended)
* Greek alphabet + Ancient Greek numbers + Ancient Greek musical notation + Byzantine musical notation


## Cheatsheets

## Regex testers
When using these websites websites, you'll see both the matches and a detailed explanation of your regular expression.

* https://regex101.com/
* http://regexr.com/
* http://myregexp.com/
* https://www.regexpal.com/

## Practice

* https://regexcrossword.com/
* https://regexone.com/

## Documentation
* [Regex in Google Docs](https://support.google.com/a/answer/1371415?hl=en)
* [Regex in Python](https://docs.python.org/3/howto/regex.html)
* [Regex in R](https://cran.r-project.org/web/packages/stringr/vignettes/regular-expressions.html)
* [Regex in Java](https://docs.oracle.com/javase/tutorial/essential/regex/)
* [Regex in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
