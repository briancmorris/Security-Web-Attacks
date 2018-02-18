# README
## Author

name: Brian Morris

email: bcmorri3@ncsu.edu

Unity id: bcmorri3

## Level 1
### Vulnerability:
The author of the webpage has hidden the flag inside of an HTML comment.
### Description:
I inspected the HTML elements by opening Chrome's webtools (F12) and clicked the elements tab. The flag could be found embedded in an HTML comment contained within the body tag. The flag is: flag{inplainsight}

## Level 2
### Vulnerability:
The author of the webpage has hidden the flag behind a password, but has not hidden the script that generates the flag.
### Description:
I inspected the HTML elements by opening Chrome's webtools (F12) and clicked the elements tab. By examining the body tag, and then the script tag, I could see the JavaScript that generates the flag's value. At the end of the script, I observed that flag is set to the value of cflag. This means that if I can determine the generated cflag, I know what the flag is. By examining the JavaScript, I saw that the string obf is split into an array of substrings by using the delimiter "_". The script then calls the JavaScript function: String.fromCharCode() for each value in the array. By looking at the documentation of String.fromCharCode(), we know that the function converts the given string to an ASCII character. By converting each of the ASCII codes stored in obf, we get the result: flag{j4v45cr1p7_15_7h3_fu7ur3}

The documentation for the function String.fromCharCode() can be found here: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode

## Level 3
### Vulnerability:
The author of the webpage allows indicates if the password is incorrect in real time. Allowing a user to easily brute-force the password.
### Description:
I noticed that when I input most characters into the password field that the page immediately loaded an error message indicating that I input the wrong password. When I cleared the password field and input the character 'f', the error message disappeared. This indicated that my input was checked against the valid password on every keystroke.

I inspected the HTML elements by opening Chrome's webtools (F12) and clicked the elements tab. I examined the body tag and started typing input to the password field. I noticed that the div tag labeled with the class "errors" only populated when an incorrect character was input. This confirmed that my input was checked in real time.

Knowing that all of the flags, so far, started with flag{ I input this string and no error message appeared. I continued to manually brute force the password until I reached the closing brace of the flag. This resulted in the flag: flag{bytebybytegoesyoursecurity}

Clicking the submit button resulted in a success message, indicating that I had found the flag.

## Level 4
### Vulnerability:
The author of the webpage has the flag revealed in the header of the server response.
### Description:
I inspected the HTML elements by opening Chrome's webtools (F12) and clicked the elements tab. While inspecting the webpage I did not notice anything out of the ordinary, so I began to experiment with burp to see what I could find.

After burp was started, I turned intercept off under the proxy tab so that the webpage could load completely. I then navigated to the homework page for problem 4. On the target tab, I expanded the drop-down menu for https://hw1.kapravelos.com, expanded the hw1 folder, then clicked the webpage labeled 4. In the center window, I clicked the response tab for webpage 4. The flag labeled X-Flag was clearly visible. The listed flag was: flag{cust0mHe@dersisthefutur3}

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
The author of the webpage allows the user to overwrite variables stored on the webpage. In particular, the variable $filename is what causes the vulnerability. By overwriting this variable, we are able to bypass the requirements to access the flag.
### Description:
First, I input a guess '1' and clicked the guess button. I noticed that the URL changed to: http://hw1.kapravelos.com:8088/index.php?attempt=1, noting that it appeared to assign a value to a variable named 'attempt'.

I inspected the HTML elements by opening Chrome's webtools (F12) and clicked the elements tab. By expanding the body tag, I observed that there was an unused anchor tag, a, that navigates to a new webpage. Notably, there is no text within the anchor tag, so the link will never appear on the webpage. By adding text, I can then click the link (or manually type in the link) to take me to a new webpage: http://hw1.kapravelos.com:8088/?hl

Here I saw that the PHP code checks my guesses (stored in $attempt) against the contents of the file: 'secret-combination.txt' (stored in $combination). Because of how the author implemented the webpage, I can overwrite the variable $filename by specifying a value within the URL to a filename that does not exist on the system. In doing so, the value of $combination is empty, and I can then insert an empty value for attempt.

By changing the URL to: http://hw1.kapravelos.com:8088/index.php?filename=blah&attempt= I overwrite $filename to be 'blah' and attempt to be an empty string. Navigating to the above URL results in a page that reveals the flag: flag{extractallthevariables!}

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
