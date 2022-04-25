
# Lab Report 2 Fixing Bugs

## Issue 1
### The code used to fix the issue
![image](./Lab%203%20First%20Error%20Fix%20.png)

### File with the failure inducing input
[Failure Inducing Input #1](https://github.com/ShoumilSarkar/markdown-parser/blob/main/test-file-2.md)

### Symptom of failure inducing input
![image](./Lab3%20First%20Error.png)

The input file that caused this error contained an extra ```]``` after the closing bracket of a link. The bug in this case is that the program could not account for brackets and parenthesis if there was no match. The symptom of this bug was that the program would get caught in an infinite loop trying to locate the matching bracket or parenthesis. Print statements were added to display the indexes of the brackets and parentheses found so far. In the output, the index of the found open and closed bracket repeat over and over.

# Issue 2
### The code used to fix the issue
![image](./Lab%203%20Second%20Error%20Fix.png)

### File with the failure inducing input
[Failure Inducing Input #2](https://github.com/ShoumilSarkar/markdown-parser/blob/main/test-file-2.md)

### Symptom of failure inducing input
![image](./Lab%203%20Second%20Error%20.png)

The bug in this follows from the fix for the previous bug. We corrected our program so that if a matching bracket or parenthesis was not found, it would break out of the while loop that checks all the characters. This was the bug, essentially anything after an incorrect link would not be checked. The symptom of this was getting an incorrect output. Any links after a link that is not valid link format due to unmatching brackets and parenthesis, were not located and output.


# Issue 3
### The code used to fix the issue
![image](./Lab%203%20Third%20Error%20Fix.png)

### File with the failure inducing input
[Failure Inducing Input #3](https://github.com/ShoumilSarkar/markdown-parser/blob/main/test-file-2.md)

### Symptom of failure inducing input
![image](./Lab%203%20Second%20Error%20.png)

Here the bug was incorrectly identifying incorrect link format as a link. The incorrect input that caused this bug contained multiple instances of the word ```"text"``` between the last ```]``` and the first ```(```. The symptom of this was that it would consider these pieces of text that are not valid markdown link format as links. It was corrected by adding the found link to the list of links only if the index of the ```(``` was equal to the index of the ```]``` plus one. This would ensure that the closing bracket and open parenthesis were right next to eachother.