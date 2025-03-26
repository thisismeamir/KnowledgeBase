---
sticker: lucide//newspaper
---

> [!IMPORTANT] Loop Invariant
> Loop invariants help us understand why an algorithm is correct. When you're using a loop invariant, you need to show three things:
> 1. **Initialization:** It is true prior to the first iteration of the loop
> 2. **Maintenance:** If it is true before an iteration of the loop, it remains true before the next iteration.
> 3. **Termination:** The loop terminates, and when it terminates, the invariant gives us a useful property that helps show that the algorithm is correct.

> “A loop-invariant proof is a form of mathematical induction, where to prove that a property holds, you prove a base case and an inductive step. Here, showing that the invariant holds before the ûrst iteration corresponds to the base case, and showing that the invariant holds from iteration to iteration corresponds to the inductive step.” (Cormen et al., 2022, p. 20)

> [!NOTE] 
> The properties look similar to induction in mathematics.
