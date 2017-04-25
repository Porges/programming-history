## Lambda functions/anonymous functions



### Language specifics

#### C#

The syntax is `(x, …) => …`, or `x => …` for single-parameter lambdas. The types of the arguments may be specified by `(T x) => …` (here, parentheses are required for single-parameter lambdas). The result type cannot be specified.

Variables are captured by reference.

Lambdas have no implicit type (so cannot be assigned to an automatically-typed variable) but are implicitly convertible to any compatible delegate type.

#### C++

The syntax is <code>[<i>captures</i>](T x, …) { … }</code>. <i>captures</i> is a ‘capture list’ that explicitly states what is captured in the closure, and whether it is captured by reference or by value. The return type may be explicitly specified with `[](T x) -> ReturnT { … }`.

The implicit type of a lambda is an unspeakable name, so in order to pass them to a function, it must be templated or take a type that hides the real type, such as `std::function`.

#### F#

The syntax is `fun x y … -> …`. Like normal functions they are curried. Type annotations can be added in the usual manner `fun (x : T) … -> …`.

Variables are captured by reference.

#### Haskell

The syntax is `\x y … -> …`. Type annotations can be added in the usual manner `\(x :: T) -> …`.

#### Java

The syntax is `(x, y) -> …` or `x -> …` for single-parameter lambdas. Types can be supplied with `(T x, …) -> …`. The result type cannot be specified.

#### Javascript

Anonymous functions are simply declared without a name: `function (x, …){ … }`.

Since ES6 (2015), the ‘arrow’ syntax can also be used: `(x, …) => …`, or `x => …` for single-parameter functions.

#### Matlab

The syntax is `@(x, …) …`.

#### Python 

The syntax is `lambda x, …: …`.

Variables are captured by reference.

### References

* Annotated Turing, p. 283–284. (About Church, has references to more references as well.)
