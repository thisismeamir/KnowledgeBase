---
sticker: lucide//newspaper
---
In this document we would try to give a solution to the sorting problem stated at [[Algorithms]]. The we would have a pseudocode to analyze it and give an estimation of how efficient it is and how the time grows with the number of sorting items.

> [!DANGER] Sorting Problem
> Given a sequence of $n$ numbers $\langle a_1,a_2, \dots, a_n\rangle$ produce a permutation (reordering) $\langle a_1' ,a_2',\dots,a_n'\rangle$ of the input sequence such that:
> $$ a_1' \leq a_2' \leq\dots \leq a_n' $$

The numbers to be sorted are also known as the keys. Although the problem is conceptually about sorting a sequence, the input comes in the form of an array with $n$ elements. When we want to sort numbers, it's often because they are the keys associated with other data, which we call *satellite data*.  Together, a key and satellite data form a *record*. 

We start with *insertion sort*, which is an efficient algorithm for sorting a small number of elements. Insertion sort works the way you might sort a hand of playing cards. Start with an empty left hand and the cards in a pile on the table. Pick up the first card in the pile and hold it with your left hand. 

then with your right hand, remove one card at a time from the pile and insert it into the correct position in your left hand. The insertion sort pseudocode would be:

```
for i = 2 to n
	key = A[i]
	// Insert A[i] into the sorted subarray A[1:i-1]
	while j > 0 and A[j] > key
		A[j+1]= A[j]
		j = j-1
	A[j+1] = key
```

A real example of this algorithm can be written in Kotlin:

```kotlin
fun main() {
	val x = mutableListOf(31.0,41.0,59.0,26.0,41.2,58.0) // Unsorted List
	(1..x.size).forEach {
		val key = x[it] // The number we want to move
		var j = it - 1 // max index up until the number
		while(j >= 0 && x[j] > key) { 
		// if the number isn't the first
		// and if the previous number is larger than the current one. 
			val y = x[j]  // Switch the two.
			x[j] = key
			x[j+1] = y
			j = j-1
		}
		x[j+1] = key // Otherwise keep the number at it's current position.
		println(x)
	}
}
```

Figure 2.2 shows how this algorithm works for an array $A$. The index $i$ indicates the *current card* being inserted into the hand. At the beginning of each iteration of the for look, which is indexed by $i$, the *subarray* consisting of elements $A[1:i-1]$  constitutes the currently sorted hand, and the remaining subarray $A[i+1:n]$  corresponds to the pile of cards still on the table.

In fact, elements $A[1:i-1]$ are the elements originally in position $1$ through $i-1$ but now in sorted order. We state these properties formally as *[[Loop Invariant]]*:


![[Pasted image 20250325151908.png]]

### Checking The Loop Invariance of Insertion Sort
1. **Initialization** We start by showing that the loop invariant holds before the first loop iteration, when $i = 2$. The subarray consists of just the single element $A[1]$, which is in fact the original element. Moreover, the subarray is sorted, which shows that the loop invariant hold prior to the first iteration of the loop.
2. **Maintenance**: Next, we tackle the second property: showing that each iteration maintains the loop invariant. Informally the body of the for loop works by moving values in $A[i-1]. A[i-2]. \dots$  and so on by one position to the right until it finds the proper position for A[i]. Incrementing $i$ for the next iteration of the for loop then preserves the loop invariant.
   
   A more formal treatment of the second property would require us to state and show a loop invariant for the while loop. Let's not get bogged down in such formalism just yet. Instead, we'll rely on our informal analysis to show that the second property holds for the outer loop.
3. **Termination**: Finally, we examine loop termination. The loop variable $i$ starts at 2 and increases by 1 in each iteration. Once $i$'s value exceeds $n$ in line $1$, the loop terminates. That is, the loop terminates once $i$ equals $n+1$. Substituting $n+1$ for $i$ in the wording of the loop invariant yields that the subarray $A[1:n]$ consists of all the initial elements but now sorted. Hence the algorithm is correct.

# Analyzing
With what we have talked about in [[Analyzing Algorithms]], how much does it take for [[Insertion Sort]]to complete? Although we can run and test the code in our own computer, but this analysis is not neat, and also not general.

Instead of running the algorithm on a programming language on a computer we can determine how long it takes by analyzing the algorithm itself. We'll examine how many times it executes each line of pseudocode and how long each line of pseudocode takes to run.

Even though the running time can depend on many features of the input, we'll focus on the one that has been shown to have the greatest effect, namely the size of the input, and describe the running time of a program as a function of the size of it's input.

## Input Size
The best notion for *input size* depends on the problem being studied. For may problems, such as sorting or computing discrete Fourier transforms, the most natural measure is the number of items in the input.  For many other problems, such as multiplying two integers, the best measure is the total number of bits needed to represent the input in ordinary binary notation.

## Running Time
The *running time* of an algorithm on a particular input is the number of instructions and data accesses executed. How we account for these costs should be independent of any particular computer. For our [[Random Access Machine]] model we assume each line takes a constant time to be executed. We assume the $k$th line takes $c_k$ time, where $c_k$ is constant.

## Analysis
To analyze the Insertion sort, lets go line by line, assign each the constant and the number of repetitions.

- `for i = 2 to n`  $\rightarrow c_1$ and $n$ times.
- `key = A[i]` $\rightarrow c_2$ and $n-1$ times.
- `j = i-1` $\rightarrow c_3$ and $n-1$ times.
- `while j > 0 and A[j] > key` $\rightarrow c_4$ and $\sum_{i=2}^n t_i$ times.
- `A[j+1] = A[j]` $\rightarrow c_5$ and $\sum_{i=2}^n (t_i - 1)$ 
- `j=j-1` $\rightarrow c_6$ and $\sum_{i=2}^n (t_i -1)$ times.
- `A[j+1] = key` and $n-1$ 

Therefore:
$$
\begin{align}
T(n) = &c_1 n + c_2 (n-1) + c_3 (n-1) \\ &+ c_4 \sum_{i=2}^nt_i +c_5 \sum_{i=2}^n(t_i-1) + c_6\sum_{i=2}^n (t_i-1) +c_7 (n-1) 
\end{align}
$$

The best case scenario happens when the array is already sorted. Therefore, we have that $t_i=1$ for all $i = 2,3,\dots,n$ and the best-case running time is given by:

$$
T(n) = (c_1 + c_2+c_3+ c_4+c_7)n - C
$$
We can express this running time as $an+b$ where $a,b$ depend on statement costs. The running time is thus a linear function of $n$.

The worst-case arises when the array is in reverse sorted order, in this case $t_i = i$. Therefore, one can show that:
$$
\begin{align}
T(n)= (\frac{c_4}{2}+\frac{c_5}{2}+\frac{c_6}{2}) n^2 + (c_1+c_2 + c_3 + \frac{c_4}{2} - \frac{c_5}{2} - \frac{c_6}{2} + c_7)n - C
\end{align}
$$
We can express this as $an^2+bn +c$ where $a,b,c$ depend on the statement costs.

## Which One We Care About?
We'll usually concentrate on finding only the *worst-case running time*, that is, the longest time for any input size of $n$. Why?
- The worst-case running time of an algorithm gives an upper bound on the running time. This feature is especially important for real-time computing, in which operations must complete by a deadline.
- For some algorithms, the worst case occurs fairly often.
- The *average case* is often roughly as bad as the worst case. 

Now we would use abstraction to make analysis easier and more meaningful,[[Order of Growth]].

---
###### Further Content
[[Analyzing Algorithms]]
[[Algorithms]]
[[Loop Invariant]]
[[Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Cliffo - Introduction to Algorithms (2022, The MIT Press) - libgen.li.pdf]]
###### Tags
#computer-science #theory #algorithms #sorting 