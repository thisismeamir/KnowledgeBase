---
sticker: lucide//newspaper
state: "[[Drafting]]"
---
In [computer science](https://en.wikipedia.org/wiki/Computer_science "Computer science"), **random-access machine** (**RAM** or **RA-machine**) is a [model of computation](https://en.wikipedia.org/wiki/Model_of_computation "Model of computation") that describes an [abstract machine](https://en.wikipedia.org/wiki/Abstract_machine "Abstract machine") in the general class of [register machines](https://en.wikipedia.org/wiki/Register_machine "Register machine"). The RA-machine is very similar to the [counter machine](https://en.wikipedia.org/wiki/Counter_machine "Counter machine") but with the added capability of 'indirect addressing' of its registers. The 'registers' are intuitively equivalent to [main memory](https://en.wikipedia.org/wiki/Random-access_memory "Random-access memory") of a common computer, except for the additional ability of registers to store natural numbers of any size. Like the counter machine, the RA-machine contains the execution instructions in the finite-state portion of the machine (the so-called [Harvard architecture](https://en.wikipedia.org/wiki/Harvard_architecture "Harvard architecture")).

The RA-machine's equivalent of the [universal Turing machine](https://en.wikipedia.org/wiki/Universal_Turing_machine "Universal Turing machine") – with its [program](https://en.wikipedia.org/wiki/Computer_program "Computer program") in the registers as well as its data – is called the [random-access stored-program machine](https://en.wikipedia.org/wiki/Random-access_stored-program_machine) or RASP-machine. It is an example of the so-called [von Neumann architecture](https://en.wikipedia.org/wiki/Von_Neumann_architecture "Von Neumann architecture") and is closest to the common notion of a [computer](https://en.wikipedia.org/wiki/Computer "Computer").

Together with the [Turing machine](https://en.wikipedia.org/wiki/Turing_machine "Turing machine") and [counter-machine models](https://en.wikipedia.org/wiki/Counter-machine_model "Counter-machine model"), the RA-machine and RASP-machine models are used for [computational complexity analysis](https://en.wikipedia.org/wiki/Computational_complexity_analysis "Computational complexity analysis"). Van Emde Boas (1990) calls these three together with the [pointer machine](https://en.wikipedia.org/wiki/Pointer_machine "Pointer machine"), "sequential machine" models, to distinguish them from "[parallel random-access machine](https://en.wikipedia.org/wiki/Parallel_random-access_machine "Parallel random-access machine")" models.

# Informal Description
An RA-machine consists of the following:

- an infinite number of [memory locations](https://en.wikipedia.org/wiki/Random-access_memory "Random-access memory") called "**registers**"; each register has an [address](https://en.wikipedia.org/wiki/Memory_address "Memory address") which is a [natural number](https://en.wikipedia.org/wiki/Natural_number "Natural number") or zero; each register can store exactly one natural number of any size, or a zero
- the **instruction table**, or just "table", containing execution instructions; the exact [instruction set](https://en.wikipedia.org/wiki/Instruction_set_architecture "Instruction set architecture") varies depending on the author; common instructions include: increment, decrement, clear to zero, copy, conditional jump, halt; other instructions are unnecessary because they can be created by combinations of instructions from the instruction set
- one special register called the "**instruction register**" (IR); this register points to the instruction being executed in the instruction table

For a description of a similar concept, but humorous, see the esoteric programming language [Brainfuck](https://en.wikipedia.org/wiki/Brainfuck).

The concept of a [random-access](https://en.wikipedia.org/wiki/Random-access "Random-access") machine (RAM) starts with the simplest model of all, the so-called [counter machine](https://en.wikipedia.org/wiki/Counter_machine "Counter machine") model. Two additions move it away from the counter machine, however. The first enhances the machine with the convenience of indirect addressing; the second moves the model toward the more conventional accumulator-based [computer](https://en.wikipedia.org/wiki/Computer "Computer") with the addition of one or more auxiliary (dedicated) registers, the most common of which is called "the accumulator".

# Formal Definition
A _random-access machine_ (RAM) is an abstract computational-machine model identical to a multiple-register [counter machine](https://en.wikipedia.org/wiki/Counter_machine "Counter machine") with the addition of indirect addressing. At the discretion of instruction from its [finite-state machine](https://en.wikipedia.org/wiki/Finite-state_machine "Finite-state machine")'s TABLE, the machine derives a "target" register's address either (i) directly from the instruction itself, or (ii) indirectly from the _contents_ (e.g. number, label) of the "pointer" register specified in the instruction.

By definition: A _register_ is a location with both an _address_ (a unique, distinguishable designation/locator equivalent to a natural number) and a _content_ – a single natural number. For precision we will use the quasi-formal symbolism from Boolos-Burgess-Jeffrey (2002) to specify a register, its contents, and an operation on a register:

- $[r]$ means "the contents of register with address $r$". The label "$r$" here is a "variable" that can be filled with a natural number or a letter (e.g. "$A$") or a name.
- $\rightarrow$ means "copy/deposit into", or "replaces", but without destruction of the source

Example: $[3] +1 → 3$; means "The contents of source register with address "3", plus 1, is put into destination register with address "3" (here source and destination are the same place). If $[3]=37$, that is, the contents of register 3 is the number "37", then 37+1 = 38 will be put into register 3.

Definition: A _direct_ instruction is one that specifies _in the instruction itself_ the address of the source or destination register whose contents will be the subject of the instruction. Definition: An _indirect instruction_ is one that specifies a "pointer register", the contents of which is the address of a "target" register. The target register can be either a source or a destination (the various $\text{COPY}$ instructions provide examples of this). A register can address itself indirectly.

For want of a standard/convention this article will specify "direct/indirect", abbreviated as "$d/i$", as a parameter (or parameters) in the instruction:

Example: $\text{COPY}( d, A, i, N )$ means directly $d$ get the source register's address (register "A") from the instruction itself but indirectly $i$ get the destination address from pointer-register N. Suppose $[N]=3$, then register 3 is the destination and the instruction will do the following: $[A] → 3$.

Definition: The contents of _source register_ is used by the instruction. The source register's address can be specified either (i) directly by the instruction, or (ii) indirectly by the pointer register specified by the instruction.

Definition: The contents of the _pointer register_ is the _address_ of the "target" register.

Definition: The contents of the _pointer register_ points to the _target register_ – the "target" may be either a source or a destination register.

Definition: The _destination register_ is where the instruction deposits its result. The source register's address can be specified either (i) directly by the instruction, or (ii) indirectly by the pointer register specified by the instruction. The source and destination registers can be one.