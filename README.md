Exercise HTML/JavaScript Template
============================
This is an HTML/JavaScript template for creating dynamic questions and answers web page.

Getting started
---------------

###Template details

Item                | Type               |Example
--------------------|--------------------|------------------------------------------
{question}          | Text               | 1. What is the capital city of Thailand?
{question number}   | Number from 1 to n | 1
{is correct choice} | Number 0 or 1      | 0
{choice}            | Text               | a. Bangkok
{answer}            | Text               | The answer is Bangkok
{answer value}      | Text               | Bangkok


###Creating multiple choice radio button

Template

```xml
<p>{question}</p>
<p><input type="radio" name="{question number}" value="{is correct choice}">{choice}</p>
<p><input type="radio" name="{question number}" value="{is correct choice}">{choice}</p>
<p><input type="radio" name="{question number}" value="{is correct choice}">{choice}</p>
<p><div id="c{question number}" ></div></p>
<p><button onClick = "showAnswer('a{question number}')">Answer</button></p>
<div id="a{question number}" style="visibility:hidden;">{answer}</div>
```

Example

```xml
<p>1. What is 1 + 1?</p>
<p><input type="radio" name="1" value="0">1</p>
<p><input type="radio" name="1" value="1">2</p>
<p><input type="radio" name="1" value="0">3</p>
<p><div id="c1" ></div></p>
<p><button onClick = "showAnswer('a1')">Answer</button></p>
<div id="a1" style="visibility:hidden;">the answer is 2</div>
```
###Creating multiple choice dropdown

Template

```xml
<p>{question}</p>
<p><select name="{question number}">
  <option value="{is correct choice}"></option>
  <option value="{is correct choice}">{choice}</option>
  <option value="{is correct choice}">{choice}</option>
  <option value="{is correct choice}">{choice}</option>
</select>
<p><div id="c{question number}" ></div></p>
<p><button onClick = "showAnswer('a{question number}')">Answer</button></p>
<div id='a{question number}' style='visibility:hidden;'>{answer}</div>
```

Example

```xml
<p>5. What is 9/3?</p>
<p><select name="5">
  <option value="0"></option>
  <option value="0">1</option>
  <option value="0">2</option>
  <option value="1">3</option>
</select>
<p><div id="c5" ></div></p>
<p><button onClick = "showAnswer('a5')">Answer</button></p>
<div id='a5' style='visibility:hidden;'>the answer is 3</div>
```

###Creating fill in the blank

Template

```xml
<p>{question}</p>
<p><input type="text" name="{question number}">
<input type="hidden" id="v{question number}" value="{answer value}" />
<p><div id="c{question number}" ></div></p>
<p><button onClick = "showAnswer('a{question number}')">Answer</button></p>
<div id="a{question number}" style="visibility:hidden;">{answer}</div>

```

Example

```xml
<p>2. What is 4 * 4?</p>
<p><input type="text" name="2">
<input type="hidden" id="v2" value="16" />
<p><div id="c2" ></div></p>
<p><button onClick = "showAnswer('a2')">Answer</button></p>
<div id="a2" style="visibility:hidden;">the answer is 16</div>

```
