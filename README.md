# README
## Author

name: Brian Morris

email: bcmorri3@ncsu.edu

Unity id: bcmorri3

## Level 1
### Vulnerability:
The author of the webpage has hidden the flag inside of an HTML comment.
### Description:
I inspected the HTML elements by opening Chrome's webtools (F12) and clicked the elements tab. The flag could be found embedded in an HTML comment contained within the <body> tag. The flag is: flag{inplainsight}

## Level 2
### Vulnerability:
The author of the webpage has hidden the flag behind a password, but has not hidden the script that generates the flag.
### Description:
I inspected the HTML elements by opening Chrome's webtools (F12) and clicked the elements tab. By examining the <body> tag, and then the <script> tag, I could see the JavaScript that generates the flag's value. At the end of the script, I observed that flag is set to the value of cflag. This means that if I can determine the generated cflag, I know what the flag is. By examining the JavaScript, I saw that the string obf is split into an array of substrings by using the delimiter "_". The script then calls the JavaScript function: String.fromCharCode() for each value in the array. By looking at the documentation of String.fromCharCode(), we know that the function converts the given string to an ASCII character. This yields the flag: flag{j4v45cr1p7_15_7h3_fu7ur3}.

The documentation for the function String.fromCharCode() can be found here: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode

## Level 3
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]

## Level 4
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]

## Level 5
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]

## Level 6
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]

## Level 7
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]

## Level 8
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]

## Level 9
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]

## Level 10
### Vulnerability:
[insert vulnerability here]
### Description:
[insert description here]
