Exercise HTML/JavaScript Template
============================
This is an HTML/JavaScript template for creating dynamic questions and answers web page.

Getting started
---------------

Creating multiple choice radio button
-------------------------------------
Template
```js
<p>{question}</p>
<p><input type="radio" name="{question number}" value="{is correct choice}">{choice}</p>
<p><input type="radio" name="{question number}" value="{is correct choice}">{choice}</p>
<p><input type="radio" name="{question number}" value="{is correct choice}">{choice}</p>
<p><div id="c{question number}" ></div></p>
<p><button onClick = "showAnswer('a{question number}')">Answer</button></p>
<div id="a{question number}" style="visibility:hidden;">{answer}</div>
```
Template values:
{question} -> Text
{question number} -> Number from 1 to n
{is correct choice} -> Number 0 or 1
{choice} -> Text
{answer} -> Text


