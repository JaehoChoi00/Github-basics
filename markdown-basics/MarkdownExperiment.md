# Markdown Basics

<img src="Markdown.png" width = 150 height = 100 style="filter: brightness(0) invert(1);">  

[:arrow_left: Return to Main README](../README.md)

> ***This is a refactored version from the `ipynb` file. With a more intuitive interface.***

## Sections:

> * [`Heading`](#heading)
>     * [`Alternative Headings`](#alternative-headings)
> * [`Simple Formatting`](#simple-formatting)
> * [`Comments`](#comments)
> * [`Bold`](#bold)
> * [`Italic`](#italic)
> * [`Strikethrough`](#strikethrough)
> * [`Bold, Italic, Strikethrough`](#bold-italic-strikethrough)
> * [`Combining Previous`](#combining-with-previous)
> * [`Blockquotes`](#blockquotes)
> * [`Lists`](#lists)
>     * [`Unordered Lists`](#unordered-lists)
> * [`Code`](#code)
>     * [`Escaping Backticks`](#escaping-backticks)
> * [`Horizontal`](#horizontal-rule)
> * [`Links`](#links)
>     * [`Formating Links`](#formatting-links)
> * [`Images`](#images) 
>     * [`Linking Images`](#linking-images)

---

## [Heading](#sections)

***Syntax:***

```md
<!-- This is a comment... Markdown file extension is .md -->

# This is a level 1 heading

## level 2 heading

### level 3 heading

#### level 4 heading

##### level 5 heading

###### level 6 heading 
```

***Result:***

> <!-- This is a comment... Markdown file extension is .md -->
> ***<- This is done using `>`***
> 
> # This is a level 1 heading
> 
> ## level 2 heading
> 
> ### level 3 heading
> 
> #### level 4 heading
> 
> ##### level 5 heading
> 
> ###### level 6 heading 

--- 

### [Alternative Headings](#sections)

---

***Syntax:***

```md

Alternative level 1 heading
===

Alternative level 2 heading
---
```

***Result:***

> Alternative level 1 heading
> ===
> 
> Alternative level 2 heading
> ---

## [Simple Formatting](#sections)

To write the [ \# ] use the escape [ \\ ]. 

Like so \\\#


## [Comments](#sections)

> \<!-- This is a comment. -->
>
> \<!-- 
> 
>     This is a multi lined comment.
> 
>     Markdown uses HTML syntax.
> 
> -->


## [Bold](#sections)

> [ **Bold text** ] Using -> \*\*Text Example**
> 
> [ __Bold text__ ] Using -> \_\_Text Example__
> 
> [ Mid **Sentence** Bold ] Using -> Text \*\*Mid Text** Text
> 
> [ Mid __Sentence__ Bold ] Using -> Text \_\_Mid Text__ Text


## [Italic](#sections)

> [ *Italicized text* ] Using -> \*Text Example*
> 
> [ _Italicized text_ ] Using -> \_Text Example_
> 
> [ Mid *Sentence* Italics ] Using -> Text \*Mid Text* Text
> 
> [ Mid _Sentence_ Italics ] Using -> Text \_Mid Text_ Text

## [Strikethrough](#sections)

> [ ~~Strikethrough~~ ] Using -> \~~Text Example~~  

## [Bold, Italic, Strikethrough](#sections)

> [ ***Bold and Italicized*** ] Using -> \*\*\*Text Example***
> 
> [ ___Bold and Italicized___ ] Using -> \_\_\_Text Example___
> 
> [ __*Bold and Italicized*__ ] Using -> \_\_\*Text Example*__
> 
> [ **_Bold and Italicized_** ] Using -> \*\*\_Text Example_**
> 
> [ Mid ***Bold and Italicized*** Sentence ] Using -> Text \*\*\*Mid Text*** Text
> 
> [ Mid ~~***Bold, Italicizied, and Strikethrough***~~ Sentence ] Using -> Text \~~\*\*\*Mid Text***~~ Text
 
## [Blockquotes](#sections)

> ### This is a block quote.


> Multiple paragraphs are possible.
>
>> This is a nested block quote. 
>
> Exit nested block quote.
> 
> # Header within block quote
> - bullet list index 1
> - bullet list index 2
>
> ### *Italics* with some text and **Bold**

## [Lists](#sections)

> 1. Numbered list index 1
> 2. Numbered list index 2
> 3. Numbered list index 3
> <!-- The number order doesn't matter -->
> 3. Numbered list index 4
> 2. Numbered list index 5
> 1. Numbered list index 6
>    1. Nested number list index 1
>    2. Nested number list index 2
>    3. Nested number list index 3
>    <!-- The number order still doesn't matter -->
>    4. Nested number list index 4
>    5. Nested number list index 5
>    6. Nested number list index 6

### 1) Can work. But it is not recommended for compatibility


## [Unordered Lists](#sections)

### The outcome is the same regardless of ***( - * + )*** is used:


***Syntax:***

```md
- Dash list index 1
  - Nested dash list index 1
  - Nested dash list index 2
- Dash list index 2
- Dash list index 3

* Asterisk list index 1
  * Nested asterisk list index 1
  * Nested asterisk list index 2
* Asterisk list index 2
* Asterisk list index 3

+ Plus list index 1
  + Nested plus list index 1
  + Nested plus list index 2
+ Plus list index 2
+ Plus list index 3

### Combination: [Best Practice. ***DON'T***]

- Dash list index 1
  - Nested dash list index 1
  * Nested asterisk list index 2
  + Nested plus list index 3
* Asterisk list index 2
+ Plus list index 3

```

***Result:***

> - Dash list index 1
>   - Nested dash list index 1
>   - Nested dash list index 2
> - Dash list index 2
> - Dash list index 3
> 
> * Asterisk list index 1
>   * Nested asterisk list index 1
>   * Nested asterisk list index 2
> * Asterisk list index 2
> * Asterisk list index 3
> 
> + Plus list index 1
>   + Nested plus list index 1
>   + Nested plus list index 2
> + Plus list index 2
> + Plus list index 3
> 
> ### Combination: [Best Practice. ***DON'T***]
> 
> - Dash list index 1
>   - Nested dash list index 1
>   * Nested asterisk list index 2
>   + Nested plus list index 3
> * Asterisk list index 2
> + Plus list index 3


## [Combining with previous](#sections)

***Syntax:***

``` md
* Asterisk list index 1 with a ***Important Message***
  * # Nested asterisk list index 1 that is a header
  * > Nested asterisk list index 2 that is a block quote
* > ### Asterisk list index 2 that has  *__all of it__*
* Asterisk list index 3
  *      Asterisk list index 1 that is a code block
  *      Done with 4 spaces [    ] or a single tab
* Asterisk list index 4 with a image <img src="Markdown.png" width = 30 height = 20 style="filter: brightness(0) invert(1);">


### Numbered list and unordered list

1. Numbered list index 1
   * Unordered asterisk list index 1
   * Unordered asterisk list index 2
2. Numbered list index 2
3. Numbered list index 3
```

***Result:***

> * Asterisk list index 1 with a ***Important Message***
>   * # Nested asterisk list index 1 that is a header
>   * > Nested asterisk list index 2 that is a block quote
> * > ### Asterisk list index 2 that has  *__all of it__*
> * Asterisk list index 3
>   *      Asterisk list index 1 that is a code block
>   *      Done with 4 spaces [    ] or a single tab
> * Asterisk list index 4 with a image <img src="Markdown.png" width = 30 height = 20 style="filter: brightness(0) invert(1);">
> 
> 
> ### Numbered list and unordered list
> 
> 1. Numbered list index 1
>    * Unordered asterisk list index 1
>    * Unordered asterisk list index 2
> 2. Numbered list index 2
> 3. Numbered list index 3


## [Code](#sections)

> ### Regular header but with <code>code</code>
> ### This is done using **\<code> code \</code>**


## [Escaping Backticks](#sections)
 
> ### Problem = [ \` code with more \`backticks\` \` ] can't be denoted on its own when in code
> * #### <code> `This is a code block with a `backtick` ` </code>
> * #### Fix:
> * #### <code> ``This is a code block with a `backtick` `` </code>


# [Horizontal Rule](#sections)

### :arrow_up: This line's :arrow_up:

> ### ***Syntax is ---***
>
> ### Like so: ⬇️
> 
> ---
> <br>

<br>

# [Links](#sections)

***Syntax:***

```md
### Link to [Markdown Guide](https://www.markdownguide.org)

## URLs and Email Addresses

<https://www.markdownguide.org>

<fake@example.com>
```

***Result:***

> ### Link to [Markdown Guide](https://www.markdownguide.org)
> 
> ## URLs and Email Addresses
> 
> <https://www.markdownguide.org>
> 
> <fake@example.com>

## [Formatting Links](#sections)

***Syntax:***

```md

This is a sentence with a **[Bolded link](<https://www.markdownguide.org>)**

This is a sentence with a *[Italicized link](<https://www.markdownguide.org>)*

To see a section on code -> \[`code`](#code) -> [`code`](#code)

Example:

To see a section on Lists -> \[`List`](#Lists) -> [`List`](#Lists)


## Reference Links

Syntax is: **\[label][reference id]** -> **[referemce id]: \<link> "Title of link"**

HTML syntax equivalent is: **\<a href="link address"> label \</a>**



Example: 
> In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"
```

***Result:***

> This is a sentence with a **[Bolded link](<https://www.markdownguide.org>)**
> 
> This is a sentence with a *[Italicized link](<https://www.markdownguide.org>)*
> 
> To see a section on code -> \[`code`](#code) -> [`code`](#code)
> 
> Example:
> 
> To see a section on Lists -> \[`List`](#Lists) -> [`List`](#Lists)
> 
> 
> ## Reference Links
> 
> Syntax is: **\[label][reference id]** -> **[referemce id]: \<link> "Title of link"**
> 
> HTML syntax equivalent is: **\<a href="link address"> label \</a>**
> 
> 
> 
> Example: 
> > In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
> of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
> eat: it was a [hobbit-hole][1], and that means comfort.
> 
> [1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"  


## [Images](#sections)

> Syntax is: **\![Label](Image path)**
> 
> HTML Syntax with resize is: **\<img src="Image path" width="100" height="100">**
>
> ---
>
> ### Syntax: \!\[Liminal Pool Image](liminal%20pools.png)
> 
> ![Liminal Pool Image](liminal%20pools.png)
>
> ---
>
> ### Syntax: img src="liminal%20pools.png" width="210" height="300">
> 
> <img src="liminal%20pools.png" width="210" height="300">


## [Linking images](#sections)

> > ### **Syntax:** 
> > **\[![Label](Image path "Image Description")](Link address to link)**
>
> ###  **Syntax**
> **\[![Liminal Pool Space]\(liminal%20pools.png "pool liminal space")](https://stoots.art/art/liminal-spaces-wasted-potential)**
> 
> [![Liminal Pool Space](liminal%20pools.png "pool liminal space")](https://stoots.art/art/liminal-spaces-wasted-potential)