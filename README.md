# What are Design Patterns?

## what it is
* Design patterns are optimized, reusable solutions to the programming problems that we encounter every day.
* It is a template that has to be implemented in the correct situation.

* "descriptions of communicating objects and classes
customized to solve a general design problem in a particular
context" - *Erich Gamma*

## what it is not

**They are not algorithms or data structures**
* provide solutions to computational problems; patterns focus on
non-functional issues like extendibility and maintainability

**They are not programming idioms**
* they are reoccurring low-level solutions to common programming
problems in a specific language; design patterns are high-level and
language independent
* idioms are looked at while coding; patterns at design time

**They are not frameworks**
* design patterns are more general than frameworks and generative;
frameworks are architectures that cannot generate solution

## There are three basic kinds of design patterns

* structural
* creational
* behavioral

**Structural** patterns generally deal with relationships between entities, making it easier for these entities to work together.

**Creational** patterns provide instantiation mechanisms, making it easier to create objects in a way that suits the situation.

**Behavioral** patterns are used in communications between entities and make it easier and more flexible for these entities to communicate.

## Periodic table of design patterns

![Periodic table of design patterns](../assets/diagrams/design-patterns-periodic-table.png)

## Anti patterns and code smells

An anti-pattern is a common reaction to a recurring
problem that is gleaned from bad experience
* An anti-pattern usually results in an ineffective and risky solution that is likely to be counterproductive
* A code smell is not buggy code
    * it is technically correct code that does not prevent the program from functioning yet it may contribute to future technical failure
    * it is a set of coding factors that indicates weaknesses in design that usually results in slowing down development, increasing risk of bugs, increasing difficulty in code maintenance and scalability
