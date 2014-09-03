Exercise HTML/JavaScript Template
============================
This is an HTML/JavaScript template for creating dynamic questions and answers web page.

Getting started
---------------

###Adding the JavaScript tag to your HTML page

```xml
<script>
var showAnswer = function(questionNumber) {
	document.getElementById(questionNumber).style.visibility = 'visible';
};

var showStatus = function(elem, correct) {
	if (correct) {
		elem.style.color = 'blue';
		elem.innerHTML = 'correct';
	} else {
		elem.style.color = 'red';
		elem.innerHTML = 'wrong';
	}
};

var checkAnswers = function(total) {
	for (var i = 1; i <= total; i++) {
		var elems = document.getElementsByName(i.toString());
		var correctElem = document.getElementById('c' + i);
		if (elems.length == 1) {
			var elem = elems[0];
			if (elem.nodeName === 'SELECT') { /*handling drop down*/
			    showStatus(correctElem, elem.options[elem.selectedIndex].value === '1');
			} else { /*handling fill in the blank*/
				showStatus(correctElem, elem.value === document.getElementById('v' + i).value);
			}
		} else { /*handling multiple choice*/
			var blank = true;
			for (var j = 0; j < elems.length; j++) {
				if (elems[j].checked) {
					showStatus(correctElem, elems[j].value === '1');
					blank = false;
					break;
				}
			}
			if (blank) {
				showStatus(correctElem, false);
			}
		}
	}
};

</script>
```


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
<p>1. What is the capital city of Thailand?</p>
<p><input type="radio" name="1" value="1">a. Bangkok</p>
<p><input type="radio" name="1" value="0">b. Phuket</p>
<p><input type="radio" name="1" value="0">c. Pattaya</p>
<p><div id="c1" ></div></p>
<p><button onClick = "showAnswer('a1')">Answer</button></p>
<div id="a1" style="visibility:hidden;">The answer is Bangkok</div>
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
<p>5. What is the capital city of Thailand?</p>
<p><select name="5">
  <option value="0"></option>
  <option value="0">a. Bangkok</option>
  <option value="0">b. Phuket</option>
  <option value="1">c. Pattaya</option>
</select>
<p><div id="c5" ></div></p>
<p><button onClick = "showAnswer('a5')">Answer</button></p>
<div id='a5' style='visibility:hidden;'>The answer is Bangkok</div>
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
<p>2. What is the capital city of Thailand?</p>
<p><input type="text" name="2">
<input type="hidden" id="v2" value="Bangkok" />
<p><div id="c2" ></div></p>
<p><button onClick = "showAnswer('a2')">Answer</button></p>
<div id="a2" style="visibility:hidden;">The answer is Bangkok</div>

```
