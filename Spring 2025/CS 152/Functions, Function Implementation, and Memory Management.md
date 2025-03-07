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
#### Fully Static Environments
- All memory allocation can be performed at load time, and the locations of all variables are fixes for the duration of the program execution
- Function an procedure definitions cannot be nested  (it is all global)
- All the information associated with a function or subroutine can be statically allocated
- Each procedure or function has a fixed activation record, which contains space for the local variables and parameters
#### Stack Based Runtime Environments
- In a block-structured language with recursion, activations of procedure blocks cannot be allocated statically
- Because a procedure may be called again before its previous activation is exited, a new activation must be created on the stack every time a block is entered and released on exit
- Several additional pieces of information are required
	- Pointer to current activation must be kept
		- This is because each procedure has no fixed location for its activation record, but the location of its activation record may vary as execution proceeds
		- This pointer must be kept in a fixed location (usually a register), and is called the environment pointer or ep, since it points to the current environment
	- Pointer to activation record of the block from which the current activation was entered
		- This is the activation of the caller in the case of a procedure call
##### Access Chaining
- When blocks are deeply nested, it may be necessary to follow more than one access link to find nonlocal reference
- Used with deep nesting
##### Limitations
###### Dangling Reference
- Any procedure that can return a pointer to a local object, either by returned value or through a pass by reference parameter, will result in a dangling reference when the procedure is exited, since the activation record of the procedure will be deallocated from the stack
##### Reference Counts
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
- Closures allow functions to retain access to their lexical scope
- Useful for maintaining state across multiple calls
- ![](Attachments/Deep%20Binding.png)
	- The function retains access to its lexical scope, meaning that it can access the variables that were in scope when the function was defined, regardless of where the function is called
### Shallow Binding
- The function resolves variables based on the current calling environment
- Less control over the variable's state compared to deep binding
- ![](Attachments/Shallow%20Binding.png)
	- Variable's most recent value is used at the time of the function call
		- Means that the function uses the current environment, which may change depending on where the function is called
### Ad Hoc Binding
- Binding can change based on how methods or functions are called
- Flexible but can lead to confusion if not managed carefully
- ![](Attachments/Ad%20Hoc%20Binding.png)
	- Variables are bound in a context-dependent manner, often determined by the specific function or usage rather than a strict lexical or dynamic scope
## Memory Management
### Dynamic Memory Management
- In a typical imperative language, automatic allocation and deallocation of storage occurs only for activation records on a stack
- Space is allocated for an activation record when a procedure is called and deallocated when the procedure is exited
- Explicit dynamic allocation and use of pointers is also available under manual programmer control using a heap of memory separate from the stack
- Manual memory management on the heap suffers from a number of potential problems, including the creation of garbage and dangling references
- Languages with significant needs for heap storage are better off leaving nonstack dynamic storage to a memory manager that provides automatic garbage collection