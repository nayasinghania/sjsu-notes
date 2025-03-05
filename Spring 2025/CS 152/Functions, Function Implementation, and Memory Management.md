---
tags:
  - cs151
---
## Procedure Definition and Activation
- Mechanism in a language for abstracting a group of actions or computations
- The group of actions is called the body of the procedure, with the body represented as a whole by the name of the procedure
- Defined by providing a specification or interface and a body
	- The specification gives the name of the procedure, a list of the types of names of its formal parameters, and the type o its returned value
### Activation
- You activate, or call, a procedure by stating its name, together with arguments to the call, which correspond to its formal parameters
#### Callee
- Call to a procedure transfers control to beginning of the body of the called procedure (the callee)
#### Caller
- When executing reaches the end of the body, control is returned to the caller
- Or with something like a return statement
### Non Local References
- References to variables declared outside of its own body
### Semantics
- A procedure is a block whose declaration is separated from its execution
### Environment
- Determines allocation of memory and maintains the meaning of names during executing
#### Activation Record
- Activation record shows where things like x and why are allocated
- Tracing back all the way to global environment
#### Defining Environment
- The environment whose context the block is in 
- Remains constant
#### Calling Environment
- Where is the block being called from
- Can change
- Dynamic environment
## Forms
### Closed Form
- Containing no non-local dependencies
- Block contained within itself
- Overloading is not a closed form
## Closure
- Resolves all outstanding nonlocal references relative to the body of the function
- One of the major tasks of a runtime environment to compute closures for all functions in cases where they are needed
## Parameters
### Formal Parameters
- Parameters without value
### Actual Parameters
- This is an argument
- The actual values for the parameters
### Parameter Passing Mechanisms
- The way in which parameters are replaced by the arguments during a call
#### Pass by Value
- The most common mechanism for parameter passing
- The arguments are expressions that are evaluated at the time of the call
- The argument values become the values of the parameters during procedure execution
- Changes can still occur outside of the procedure (e.g. pointers or reference types)
#### Pass by Reference
- Passing variable location instead of passing the value
- An argument must be like a variable with an allocated address
- The parameter becomes an alias for the argument
- An changes made to the parameter occur to the argument as well
##### Multiple Aliasing
- See slides
#### Pass by Value-Result
- Similar result to pass by reference, except no actual alias is established
- The argument value is copied and used in the procedure
	- Then, the final value of the parameter is copied back to the location of the argument when the procedure exits
- Also known as copy-in copy-out or copy-restore
#### Pass by Name and Delayed Evaluation
- Argument not evaluated until its actual use as a parameter in the called procedure
### Translator
- A translator can prevent many violations of these parameter specification
### Type Checking
## Binding
### Deep Binding
### Shallow Binding
### Ad Hoc Binding