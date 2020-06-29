# Coverage counters

## Instructions (C0 Coverage)
The smallest unit JaCoCo counts are single Java byte code instructions.

## Branches (C1 Coverage)
JaCoCo also calculates branch coverage for all if and switch statements.
This metric counts the total number of such branches in a method and determines the number of executed or missed branches.
Note that exception handling is not considered as branches in the context of this counter definition.

## Lines
For all class files that have been compiled with debug information, coverage information for individual lines can be calculated. 
A source line is considered executed when at least one instruction that is assigned to this line has been executed.

## Cyclomatic Complexity (from [here](https://www.eclemma.org/jacoco/trunk/doc/counters.html))
JaCoCo also calculates cyclomatic complexity for each non-abstract method and summarizes complexity for classes, packages and groups.
According to its definition by McCabe1996 cyclomatic complexity is the minimum number of paths that can, in (linear) combination, generate all possible paths through a method.
Thus the complexity value can serve as an indication for the number of unit test cases to fully cover a certain piece of software.
Complexity figures can always be calculated, even in absence of debug information in the class files.

The formal definition of the cyclomatic complexity v(G) is based on the representation of a method's control flow graph as a directed graph:

v(G) = E - N + 2

Where E is the number of edges and N the number of nodes. 
JaCoCo calculates cyclomatic complexity of a method with the following equivalent equation based on the number of branches (B) and the number of decision points (D):

v(G) = B - D + 1

Based on the coverage status of each branch JaCoCo also calculates covered and missed complexity for each method.
Missed complexity again is an indication for the number of test cases missing to fully cover a module.
Note that as JaCoCo does not consider exception handling as branches try/catch blocks will also not increase complexity.
