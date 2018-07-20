# sy4
## A JavaScript evaluation notation language

Sy4 is a simple JSON format to enable evaliation in JavaScript.

Sy4 is a definition of the required formula it does not actaully perform any actions - use asssassin and envoy for this

In its simplest form it consists of an array with an action and parameters. 

__["+",1,2]__

__This will be evaluated by enigma as evaluate to 3__
 
 Sy4 expressions can be nested and are evaluated from the inside out.

 __["+",1,["-",3,2]]__

__This will be evaluated as ["+",1,1] then 2.__
There is no limit to the level of nesting

Sy4 expressions can include variables which need to be evaluated with sp1

__["+",1,"a"] where a is in an object passed to sp1 with a value of 7__

__Gets converted by sp1 by looking up the data to  ["+",1,7]__

__which will be evaluated by enigma as 8__

Sp1 variables can be nested objects by using an object with the key "o" containing an array that contains the nesting

__["+",{"o":["a","b"]}, 1]__

__The data passed to sp1 will be checked for the key a.b__

## Supported Methods
### v 0.0
\+ addition

\- subtraction

\* multiplication

\/ division

\== equality

\!= inequality

\= evaluation (retuns the first parameter without processing)


