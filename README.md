# sy4
## An evaluation lotation language

Sy4 is a simple JSON format  to enable evaliation in JavaScript.

Sy4 is a definition of the required formuala it does not actaully perform any actions - use enigma and sp1 for this

In its simplest form it consists of an array with an action and parameters. 

  _["+",1,2]_

 _This will be evaluated by enigma as evaluate to 3_

 
 Sy4 expressions can be nested and are evaluated from the inside out.

 _["+",1,["-",3,2]]_

 _This will be evaluated as ["+",1,1] then 2_
There is no limit to the level of nesting

Sy4 expressions can include variables which need to be evaluated with sp1

_["+",1,"a"] where a is in an object passed to sp1 with a value of 7_

_Gets converted by sp1 by looking up the data to  ["+",1,7_]

_which will be evaluated by enigma as 8_

Sp1 variables can be nested objects by using an object with the key "o" containing an array that contains the nesting

_["+",{"o":["a","b"]}, 1]_

_The data passed to sp1 will be checked for the key a.b_

## Supported Methods
### v 0.0
\+ addition

\- subtraction

\* multiplication

\/ division

\== equality

\= evaluation (retuns the first parameter without processing)

