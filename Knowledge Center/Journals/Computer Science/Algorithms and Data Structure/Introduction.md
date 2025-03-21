---
undefined: ""
File: Knowledge Center/Journals/Computer Science/Algorithms and Data Structure/Role of Algorithms in Computing.md
---
This note is dominantly about how to know if you're developing the right algorithm. When designing algorithms, it's important to know how they operate and how to design them. In addition to that we need mathematics to show that our algorithm 1) works correctly, and 2) do it efficiently.

# Algorithms
*Informal Definition of Algorithm*: Algorithm is a well-defined (need to define what we mean here) set of computational procedure that takes some input, and produces an output in a finite amount of time.

Suppose that we need to sort a sequence of numbers into monotonically increasing order. This problem arises frequently in practice and provides fertile ground for introducing many standard design techniques and analysis tools.

> [!DANGER] Sorting Problem
> Given a sequence of $n$ numbers $\langle a_1,a_2, \dots, a_n\rangle$ produce a permutation (reordering) $\langle a_1' ,a_2',\dots,a_n'\rangle$ of the input sequence such that:
> $$ a_1' \leq a_2' \leq\dots \leq a_n' $$

Such an input sequence is called an *instance* of the sorting problem. In general, an *instance of a problem* consists of the input needed to compute a solution to the problem.

Sorting is a fundamental operation in computer science. Because many programs use it as an intermediate step. Because of this we have a lot of different sorting algorithms, but to choose the right one for your task, needs analysis and context.


> [!IMPORTANT] Definition of Correct Algorithm
> An algorithm is correct, if for every problem instance provided as input, it *halts* and outputs the correct solution to the problem instance.

Algorithms are used everywhere in computer science and usages that people have for computers. After all it is the cornerstone of computation. There is two characteristics common to many interesting algorithmic problems:
1. They have many candidate solutions, the overwhelming majority of which do not solve the problem at hand. Finding one that does, or one that is "best", without explicitly examining each possible solution, can present quite a challange.
2. They have practical applications. 

> [!DANGER] Note
> Not every problem solved by algorithms has an easily identified set of candidate solutions. 

## Data Structires
A *data structure* is a way to store and organize data in order to facilitate access and modifications. Using the appropriate data structures is an important part of algorithm design. No single data structure works well for all purposes, and so you should know the strengths and limitations of several of them.


## Hard Problems
There are some problems, for which we know of no algorithm that runs in a reasonable amount of time. They are called NP-Problem, they are interesting  because although no efficient algorithm of them has been found, no one has actually proved that there exists none. 

Secondly NP-Complete problems has the remarkable property that if an efficient algorithm exits for any one of them, then efficient algorithms exist for all of them. This relationship among the NP-complete problems makes the lack of efficient solutions all the more tantalizing.

Thirdly, several NP-complete problems are similar, but not identical, to problems for which we do know of efficient algorithms. Computer scientists are intrigued  by how small change to the problem statement can cause a big change to the efficiency of the best known algorithm.

# Algorithms as a Technology

## Efficiency
Different algorithms devised to solve the same problem often differ dramatically in their efficiency. These differences can be much more significant than differences due to hardware and software.

Total system performance depends on choosing efficient algorithms as much as on choosing fast hardware. Just as rapid advances are being made in other computer technologies, they are being made in algorithms as well. You might wonder whether algorithms are truly that important on contemporary computers in light of other advanced technologies. 

The answer is yes. Although some applications do not explicitly require algorithmic content at the application level, many do. 