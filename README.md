Exercise HTML/JavaScript Template
============================
This is an HTML/JavaScript template for creating dynamic questions and answers web page.

Getting started
---------------

Replace appropriate values to the following the desire template

Template values:

Item                | Description
--------------------|-------------
{question}          | Text
{question number}   | Number from 1 to n
{is correct choice} | Number 0 or 1
{choice}            | Text
{answer}            | Text


1. Creating multiple choice radio button

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

2. Creating multiple choice dropdown

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
