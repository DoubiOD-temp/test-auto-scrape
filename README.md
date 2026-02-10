# Proving Algorithm Correctness with Loop Invariants

In computer science, writing an algorithm that _seems_ to work is not enough. We need a formal way to **prove** it is correct. The primary technique for doing this — especially for iterative algorithms — is the **Loop Invariant**.

---

## 1. What Is a Loop Invariant?

A **loop invariant** is a property or condition that is true **before and after every iteration** of a loop. It acts as a logical anchor: if we can show that this property holds throughout the entire execution, we can conclude that the algorithm produces the correct result.

Think of it as a contract the loop must honor on every pass.

---

## 2. The Three Steps of a Loop Invariant Proof

To prove an algorithm correct using a loop invariant, we must establish three things — mirroring the structure of **mathematical induction**:

### Initialization (Base Case)

The invariant is true **before the first iteration** of the loop (i.e., when the loop variable is at its initial value).

### Maintenance (Inductive Step)

If the invariant is true **before** an iteration, it remains true **after** that iteration. This is the core of the proof — show that one step of the loop preserves the property.

### Termination

When the loop terminates, the invariant — combined with the loop's exit condition — gives us a useful property that proves the algorithm's **correctness**.

> **Key Insight**: Unlike pure mathematical induction, the termination step is critical. We must show that the loop actually _stops_ and that the invariant at that point implies the desired result.

---

## 3. Classic Example: Insertion Sort

Consider the Insertion Sort algorithm over an array $A[1 \ldots n]$:

```
for j = 2 to n:
    key = A[j]
    i = j - 1
    while i > 0 and A[i] > key:
        A[i + 1] = A[i]
        i = i - 1
    A[i + 1] = key
```

### The Loop Invariant

> At the start of each iteration of the outer `for` loop, the subarray $A[1 \ldots j-1]$ consists of the elements originally in $A[1 \ldots j-1]$, but in **sorted order**.

### Proof

**Initialization**: Before the first iteration ($j = 2$), the subarray $A[1 \ldots 1]$ contains a single element. A single element is trivially sorted. ✅

**Maintenance**: Assume $A[1 \ldots j-1]$ is sorted before iteration $j$. The inner `while` loop shifts elements larger than `key` one position to the right and then inserts `key` into its correct position. After this, $A[1 \ldots j]$ is sorted. The invariant holds for the next iteration. ✅

**Termination**: The loop terminates when $j = n + 1$. Substituting into the invariant: $A[1 \ldots n]$ is sorted. This is the entire array — the algorithm is correct. ✅

---

## 4. Another Example: Linear Search

```
for i = 1 to n:
    if A[i] == target:
        return i
return NOT_FOUND
```

### The Loop Invariant

> At the start of iteration $i$, the element `target` is **not present** in $A[1 \ldots i-1]$.

### Proof

**Initialization**: Before the first iteration ($i = 1$), the subarray $A[1 \ldots 0]$ is empty. The target is trivially not in an empty subarray. ✅

**Maintenance**: If we reach iteration $i$, none of $A[1], A[2], \ldots, A[i-1]$ matched the target (otherwise we would have returned). So the invariant holds: target is not in $A[1 \ldots i-1]$. If $A[i]$ matches, we return correctly. If not, the invariant extends to $A[1 \ldots i]$ for the next iteration. ✅

**Termination**: If the loop ends without returning ($i = n + 1$), the invariant tells us the target is not in $A[1 \ldots n]$ — the entire array. Returning `NOT_FOUND` is correct. ✅

---

## 5. Partial vs. Total Correctness

|                         | Definition                                                           |
| :---------------------- | :------------------------------------------------------------------- |
| **Partial Correctness** | _If_ the algorithm terminates, it produces the correct result.       |
| **Total Correctness**   | The algorithm **always terminates** AND produces the correct result. |

A loop invariant proof that includes a valid **termination** argument proves **total correctness**. Without termination, you only have partial correctness — the algorithm might loop forever.

---

## 6. Tips for Choosing a Good Invariant

1. **Start from the postcondition**: What do you want to be true when the loop ends? Your invariant should be a generalized version of that goal.
2. **Relate it to progress**: The invariant should capture what fraction of the work is "done" at each step.
3. **Keep it simple**: If your invariant is too complex, you may be overcomplicating the proof. A good invariant is a clean, concise statement.
4. **Test it mentally**: Walk through 2–3 iterations by hand and check that the invariant actually holds.
