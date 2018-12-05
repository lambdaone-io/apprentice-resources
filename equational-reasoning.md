Equational reasoning
====================

**Tags**: *substitution model*, *referential transparency*, *purity*, *side effect*

Concerning programming, we can say that a function definition limits the scope where different expressions are evaluated in order to produce a result. This result is produced by the transformation of its input parameters (if they exist) along with any other internal variables and defines the return type of that function.

For developers it seems very convenient to be able to `reason` about a function (i.e. understand what the function does ) just by checking the input and the output of the function [[1]](#comments). This is to say that a function's return value represents the transformation of its internal state by potentially using other arguments as its parameters.

However what a function does is not always related to the value that it returns and this is the case when a function has side effects. This is when we say that a function is not `pure`. By side effect we mean any kind of interaction that a function has with the outside word (i.e. outside of its scope ). This can be IO operations, altering state of external variables etc. As a result, the only way to reason about what the function does is to deep dive into the definition of the function and monitor what happens when a side effect operation happens.

This breaks `referential transparency` meaning that what a function does is no more represented **only** by the value that it takes and that it returns [[2]](#comments). When referential transparency exists we can replace a function / expression with the value that returns thus being able to reason about our programs just by substituting the expressions we have with the values they return ( similar to the evaluation of mathematical equations ). This is what we call the `substitution model`. In other words we can say that `referential transparency` is the key that enables a natural way of reasoning ( according to mathematics ) based on `substitution model` by substituting equals with equals ( i.e. variables with/or referents with values). This is what we call in other words `equational reasoning`.

## Resources

1. Functional Programming in Scala (book), Chapter 1 : What is functional programming.

## Challenges

1. Give examples of side effect operations.

2. Give the definitions of the terms:  
  a. referential transparence  
  b. substitution model  
  c. equational reasoning  

### Comments
1. This means that in order to reason precisely we should not have redundant input parameters and any side effects. As a result the function can be seen as a transformation of some input values to the result value. The interesting thing to notice here is what happens in the two corner cases, i.e. when there are no input parameters or nothing to be returned. The answer is that in pure functions this means that either a single transformation is performed (no input corresponds to a unique input) or no transformation at all (no result corresponds to a single result). This means after all that there is a single value that can substitute such functions.
2. Referential transparency brings the two worlds of mathematics and programming much closer in terms of functions. This is to say that the set of input values of a programming function can be seen as the `input set` or `domain` of a mathematical function and that the result values can be seen as the `target set` or `codomain` respectively.
