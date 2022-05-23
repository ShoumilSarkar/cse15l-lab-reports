# Lab Report 4

## Repo Links

### My Markdown Parse
[My Markdown Parse](https://github.com/ShoumilSarkar/markdown-parser)

### Markdown Parse reviewed in Week 7
[Reviewed Markdown Parse](https://github.com/JasonMorris1/markdown-parser)


## Testing Snippets

### Snippet 1

Expected output:
![Snippet One Expected](./Snippet%201%20Expected%20Preview.png)

>We determine that the links Markdown expects from the file are, "`google.com","google.com", and "ucsd.edu".

#### Snippet 1 Test
![Snippet 1 Test](./Snippet%201%20Test%20.png)

#### My Markdown Parse
![Snippet One My Parser](./My%20Parser%20Snippet%201%20Test.png)


We see that it fails on my version of Markdown Parse because it incorrectly finds ```url.com``` and does not find ```ucsd.edu```.


#### Reviewed Markdown Parse
![Snippet One Reviewed Parser](./Snippet%201%20Reviewed%20Test.png)


We see that the reviewed Markdown Parse fails because it does not find any urls in the file.


### Snippet 2

Expected output:
![Snippet Two Expected](./Snippet%202%20Expected%20Preview.png)

>We determine that the links Markdown expects from the file are, "a.com","a.com(())", and "example.com".

#### Snippet 2 Test
![Snippet 2 Test](./Snippet%202%20Test.png)

#### My Markdown Parse
![Snippet Two My Parser](./My%20Parser%20Snippet%202%20Test.png)

We see that it fails on my version of Markdown Parse because it only finds ```a.com``` and does not find ```a.com(())``` and ```example.com```.


#### Reviewed Markdown Parse

![Snippet Two Reviewed Parser](./Snippet%202%20Reviewed%20Test.png)


We see again that the reviewed Markdown Parse fails because it does not find any urls in the file.



### Snippet 3

Expected output:
![Snippet Three Expected](./Snippet%203%20Expected%20Preview.png)

>We determine that the only link Markdown expects from this file is, "https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule".

#### Snippet 3 Test
![Snippet 3 Test](./Snippet%203%20Test.png)

#### My Markdown Parse
![Snippet Three My Parser](./My%20Parser%20Snippet%203%20Test.png)


We see that it fails on my version of Markdown Parse because it incorrectly finds  `https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule` with the spaces and page breaks as well as incorrectly finds `https://www.twitter.com`.


#### Reviewed Markdown Parse
![Snippet Three Reviewed Parser](./Snippet%203%20Reviewed%20Test.png)


We see that the reviewed Markdown Parse fails because it finds both `https://www.twitter.com` and `https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule` when it should only find the latter.

### Questions

- I believe that a small code change will allow my Markdown Parser to work. I would have to add functionality that ignores brackets that are surrounded by backticks.
- A small code change would correct the Markdown parser to work for Snippet 2 and related cases. Essentially start the index of the closing parentheses at the index before the next open bracket and iterate this index backwards to try and find a closing parentheses. The closing bracket should be the next valid closing bracket and ensure that the open parentheses appears right after the closing bracket.
- Getting the code working for Snippet 3 and related cases would also be a small change. Code that ensure there are no line breaks anywhere between the open bracket to the closing parentheses will need to be added. The trim() function also needs to be used on links before they are placed into the ArrayList of found links.