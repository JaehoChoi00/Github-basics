# Extended Syntax

<img src="Markdown.png" width = 150 height = 100 style="filter: brightness(0) invert(1);">  

[:arrow_left: Return to Main README](../README.md)

> ***This is a refactored version from the `ipynb` file. With a more intuitive interface.***

## Sections:

> * [`Tables`](#tables)
>     * [`Text Alligment`](#text-allignment)
>     * [`Nested Tables`](#nested-table)
>     * [`Formatting Text in Tables`](#formatting-text-in-tables)
>     * [`Table Generator`](#table-generator)
>     * [`Side Project`](#side-project--table-generator-using-python)
> * [`Syntax Highlighting`](#syntax-highlighting)
> * [`Footnotes`](#footnotes)
> * [`Task Lists`](#task-lists)
> * [`Emoji`](#emoji)


## [Tables](#sections)

***Syntax:***

```md:
| Column 1    | Column 2    | column 3    |  
| ----------- | ----------- | ----------- |  
| Row 1 Col 1 | Row 1 Col 2 | Row 1 Col 3 |  
| Row 2 Col 1 | Row 2 Col 2 | Row 2 Col 3 |
```

***Result:***

> | Column 1 | Column 2 |
> | -------- | --------- |
> | Row 1 Col 1 | Row 2 Col 2 |
> | Row 2 Col 1 | Row 2 Col 2 |

<br>

### [Text allignment](#sections)

```md
| Column 1    | Column 2    | column 3    |  
| :-----------: |:----------- | -----------: |  
| Row 1 Col 1 | Row 1 Col 2 | Row 1 Col 3 |  
| Row 2 Col 1 | Row 2 Col 2 | Row 2 Col 3 |
```

> | Column 1    | Column 2    | column 3    |  
> | :-----------: |:----------- | -----------:|  
> | Row 1 Col 1 | Example     | Example     |  
> | Row 2 Col 1 | Row 2 Col 2 | Row 2 Col 3 |


<br>

### [Nested table](#sections)

```md
| Outer Header 1 | Outer Header 2 |  
| -------------- | -------------- |  
| Normal Cell    | <table><tr><th>Inner H1</th><th>Inner H2</th></tr><tr><td>Data 1</td><td>Data 2</td></tr></table> |
```

> | Outer Header 1 | Outer Header 2 |
> | -------------- | -------------- |
> | Normal Cell    | <table><tr><th>Inner H1</th><th>Inner H2</th></tr><tr><td>Data 1</td><td>Data 2</td></tr></table> |
> 
> ---
> 
> **Inner Table Syntax:**  
> 
> \<table>\<tr>\<th>Inner H1\</th>\<th>Inner H2\</th>\</tr>\<tr>\<td>Data 1\</td>\<td>Data 2\</td>\</tr>\</table>

<br>

### [Formatting text in tables](#sections)

***Syntax:***

```md
| Style | Syntax | Example |
| :--------------| :-------------- | :-------------- |
| [Link](www.example.com) | `[Text](link)` | [Google](www.google.com) |
| **Bold** | `**text**` | **Important** |
| *Italic* | `*text*` | *Draft* |
| ~~Strikethrough~~ | `~~text~~` | ~~Old Value~~ |
| `Code` | `` `text` `` | `id_num` |
| Combined | `***bold & italic***` | ***Critical*** |
| Pipe Character [ &#124; ] | \&#124; | &#124; |
```

***Result:***

> | Style | Syntax | Example |
> | :--------------| :-------------- | :-------------- |
> | [Link](www.example.com) | `[Text](link)` | [Google](www.google.com) |
> | **Bold** | `**text**` | **Important** |
> | *Italic* | `*text*` | *Draft* |
> | ~~Strikethrough~~ | `~~text~~` | ~~Old Value~~ |
> | `Code` | `` `text` `` | `id_num` |
> | Combined | `***bold & italic***` | ***Critical*** |
> | Pipe Character [ &#124; ] | \&#124; | &#124; |


### [Table Generator](#sections)

<https://www.tablesgenerator.com/markdown_tables>

## Side Project : Table Generator using Python

> [Reference](https://www.geeksforgeeks.org/python/printing-lists-as-tabular-data-in-python/)

```py
# Table Generator

# Edit these values to change the output of the table.

rows = 10
cols = 10
width = 3

maxlength = 0
matrix = []

STARTOFCOLUMN = '|'
ENDOFCOLUMN = '|'
HEADERFILLER = '-'

matrix = [["" for _ in range(cols)] for _ in range(rows)]

final_syntax = ""

# This does absolutely nothing at the moment because there is no cell value feature yet
def variableMiddle(width, variable):
    periods = width - len(variable)
    processed = ""
    if (periods <= 0):
        processed = variable
    else:
        processed = " " * (periods - (periods//2)) + variable + " " * (periods//2)
    return processed

# This is for future challenge in making an interface where the user can add variables in the cells.
def getLargestVariable():
    global maxlength
    maxlength = 0 
    for i in range (rows):
        for j in range (cols):
            variable = str(matrix[i][j])
            if (len(variable) > maxlength):
                maxlength = len(variable)
                
    return maxlength

def generateTable():

    final_syntax = STARTOFCOLUMN + " "
    for i in range (cols):
        val = str(matrix[0][i]) if rows > 0 else ""
        final_syntax = final_syntax + variableMiddle(width, val) + ' ' + ENDOFCOLUMN + ' '
    final_syntax = final_syntax + " \n" + STARTOFCOLUMN + " "
    
    for i in range (cols):
        final_syntax = final_syntax + "-" * width + ' ' + ENDOFCOLUMN + ' '
    final_syntax = final_syntax + " \n"
    
    for i in range (1, rows):
        final_syntax = final_syntax + STARTOFCOLUMN + ' '
        for j in range (cols):
            final_syntax = final_syntax + variableMiddle(width, str(matrix[i][j])) + ' ' + ENDOFCOLUMN + ' '
        final_syntax = final_syntax + " \n"
    final_syntax = final_syntax + "  \n"
    return final_syntax

print(generateTable()) 
```

```bash
# Generated Result: 

|     |     |     |     |     |     |     |     |     |     |  
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     |  
|     |     |     |     |     |     |     |     |     |     | 
```


## [Syntax Highlighting](#sections)

### Full Syntax  

> ````  
> ```langage  
> Whatever code  
> ```  
> ````   

### Example

> ### **bash:**
> 
>> ***Syntax:***
>> ````  
>> ```bash  
>> git add .  
>> git commit -m "This is a commit message"  
>> ```  
>> ````
>
>> ***Result:***
>> ```bash
>> git add .
>> git commit -m "This is a commit message"
>> ```
> <br>

> ### **json:**
> 
>> ***Syntax:***
>> ````  
>> ```json  
>> {
>>  "1st variable name": "1st variable",
>>  "2nd variable name": "2nd variable",
>> } 
>> ```  
>> ````
>
>> ***Result:***
>> ```json
>> {
>>  "1st variable name": "1st variable",
>>  "2nd variable name": "2nd variable",
>> }
>> ```
> <br>

> ### **java:**
>
>> ***Syntax*** 
>> ````
>> ```java
>> public class javaClass {
>>     public static void main(String[] args) {
>>       System.out.println("This is a java code");  
>>   }
>> }
>> ```
>> ````
>
>> ***Result:***
>> ```java
>> public class javaClass {
>>     public static void main(String[] args) {
>>       System.out.println("This is a java code");  
>>   }
>> }
>> ```
> <br>

---

## [Footnotes](#sections)

***[Extension in vscode is needed to enable footnote in preview.]***

***Syntax:***  

```md
Random sentence [^footnote] filler sentence.[^bignote]

[^footnote]: This is the first footnote.

[^bignote]: This is a footnote with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ code }`

    More sentences

```

***Result:***

Random sentence [^footnote] filler sentence.[^bignote]


## [Task Lists](#sections)

***Syntax:***

```md
- [x] Todo list item 1  
- [ ] Todo list item 2  
- [ ] Todo list item 3   
```

***Result:*** 

> - [x] Todo list item 1  
> - [ ] Todo list item 2  
> - [ ] Todo list item 3   


## [Emoji](#sections)

***Syntax***

```md
:emoji_Shortcodes:  
```

***Result:***

> :smile::wave:
>
> or
>
> Direct copy and past online: 😭  
> 
> <br>


[^footnote]: This is the first footnote.

[^bignote]: This is a footnote with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ code }`

    More sentences