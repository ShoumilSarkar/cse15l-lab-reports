# Lab Report 5 Different Outputs

## Finding the Differences

For each implementation, a bash script to run the markdown-parser in a loop for all md files in the `test-files` directory was run with output redirection. The command used was, `bash script.sh > results.txt`. This takes the output from running the bash script and puts it all into a txt file called `results.txt`. Now that there is a results file for both implementations, the command `vimdiff markdown-parser/results.txt cse15lsp22-markdown-parser/results.txt` can be used to have vim highlight all the differences between the two outputs.


## First Difference

The first difference to go over was found in test-file 490.
[Test-File 490](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/490.md)

![Test-File 490 Comparison](./Lab%20Report%205%20Test-File%20490%20Diff.png)

We see that the Lab 9 implementation gives a result of no link found, `[]`. My version of the markdown parser gives a link result of `[<foobar>]` with a line break between the `foo` and the `bar`. The given implementation is correct and my version is incorrect. There should be no link to be found because there is a line break so the output should just be an empty string array`[]`. 

![Problem Two](./Lab%20Report%205%20Fix%201.png)

A fix for this can be placed into the code here. The string with the found link needs to be checked to make sure it does not contain a line break character. If it does not contain a line break character then it can be added to the list of links found in the file.



## Second Difference


The second difference found to go over is the output of test-file 201.

[Test-File 201](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/201.md)

![Test-File 201 Comparison](./Lab%20Report%205%20Test-File%20201%20Diff.png)

The given Lab 9 implementation gives an output of `[baz]`. My parser's output was no links found, `[]`. For this file, my implementation is correct because there should not be any links found. This is because between the last `]` and the `(` there is the string `: <bar>`, these characters being in between makes this an invalid link format so no link should be found.

![Problem Two](./Lab%20Report%205%20Fix%202.png)

To fix this, it needs to be verified that the open parentheses character comes immediately after the close bracket character. This can be added as a condition to the if statement in the code with something like `closeBracket+1==openParen`. This will ensure that it is only a valid link if the closed bracket and open parenthesis are right next to each other.