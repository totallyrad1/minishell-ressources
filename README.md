# minishell-rassources

how to make your own shell: https://www.cs.purdue.edu/homes/grr/SystemsProgrammingBook/Book/Chapter5-WritingYourOwnShell.pdf

this blog explains how to build an interpreter, you can use the explination to implement a shell command interpreter using trees and left decent recursion parser https://ruslanspivak.com/lsbasi-part1/

https://solarianprogrammer.com/2018/01/10/writing-minimal-x86-64-jit-compiler-cpp/

also, this playlist explains how to write an interpreter in C

[https://www.youtube.com/watch?v=WABO4o_y8qc&ab_channel=Ian](https://www.youtube.com/watch?v=WABO4o_y8qc&ab_channel=Ianertson)

here's a  diagram that simplify the understanding of the tokenizer algorithm as a first step in MiniShell project ( made by me and **@nakebli**) 

[tokenizer_2.tldr](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b41e626d-1a8e-4007-a0e5-be048715a8e1/tokenizer_2.tldr)

that was in a general context you could start from here though 

resurses https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html

1967523

an algorithm where I have a a doubly linked list as input and this linked list contains commands like “ls -ls, echo, cat, grep ..” tokenized as “WORD” in a node and command like “|, &&, ||, >, >>, < <<” tokenized in each by a name in a single node and also space tokenized as “SPACE” in a node but only when its between “WORD”, I want to take this input and using recursive descent parsing to take the doubly linked list ant turn it into a syntax tree, I want something like this layout of functions I made “”

what I'm doing in the parsing : I have a doubly linked list filled with tokens (commands)

the main function for implementing recursive descent parsing called build_tree

this function takes the linked list and call the first function from the chained function to handle every case in the command line, it calls the and_or_case() function that handles the case when the content of the node is “&& or ||”, what this function do is at first it calls another function who handles pipe “|” we do this so that the command with the most precedent ends up the top of the tree, then I check if the content of the node is “&& or ||” if yes
