Exploiting tiny-js
=======

[Original Project](https://code.google.com/p/tiny-js/)

This is mainly going to be an attempt at hopefully finding and exploiting a bug in tiny-js

My Description of Tinyjs
---
Tinyjs is an implementation of js that is done in a single file (~2000 lines).<br />
It is intended to be used as a library, and in fact the REPL is [Script.cpp](https://github.com/sS3lla/tiny-js/blob/master/Script.cpp),
which is done via evalulating each expression.


Internal Structure
------------------------

TinyJS uses a Recursive Descent Parser (RDP) to generate tokens. <br/>
An extremly basic description of RDP is that it advances a cursor and does a big if statement.

The RDP generates tokens, which are then directly executed from, rather than a vm.<br/>
The execution of the tokens is done via (Need to check this out)

Variables, Arrays and Objects are stored in a simple linked list tree structure. (Need to check this out)

Project Structure
------------------------
[Script.cpp](https://github.com/sS3lla/tiny-js/blob/master/Script.cpp)
-> REPL<br/>
[TinyJS.cpp](https://github.com/sS3lla/tiny-js/blob/master/TinyJS.cpp)
-> Main JS script <br/>
[TinyJS_Functions.cpp](https://github.com/sS3lla/tiny-js/blob/master/TinyJS_Functions.cpp)
-> Native General Functions<br/>
[TinyJS_MathFunctions.cpp](https://github.com/sS3lla/tiny-js/blob/master/TinyJS_MathFunctions.cpp)
-> Specific Math Functions (Not added by default)<br/>
[run_tests.cpp](https://github.com/sS3lla/tiny-js/blob/master/run_tests.cpp)
-> Evaluates a whole file and checks if ```result = 1``` which is set by the script and counts that as a pass


Existing/reported bugs
--------------------------------
I am currently looking at this [issue](https://github.com/gfwilliams/tiny-js/issues/31), which I have minifed down to ```x = a?b = 1 ? 1 : anything_can_be_here```<br/>
I still however don't know how it gets triggered


