# 📊 Difference Array Technique

## 📌 What is it?

Imagine you have an array (maybe filled with zeros), and you're asked to perform multiple **range updates** like:

> "Add `x` to all elements from index `l` to `r` (inclusive)."

You need to do this efficiently and **avoid querying the array in between**. At the end, you'll output the final updated array.

---

## ❌ Brute Force Approach

For each update `(l, r, x)`, we loop through the array and add `x` to all elements between `l` and `r`.

### ⏱️ Time Complexity

- For `Q` queries on an array of size `N`: **O(Q × N)**
- ❌ Too slow!

### 🔍 Simple Example

```ts
let arr = [0, 0, 0, 0, 0];
let queries = [
  [1, 3, 2], // Add 2 to indices 1 to 3
  [2, 4, 3], // Add 3 to indices 2 to 4
];

for (let [l, r, x] of queries) {
  for (let i = l; i <= r; i++) {
    arr[i] += x;
  }
}
console.log(arr); // [0, 2, 5, 5, 3]
```

---

## ⚡ Optimized: Difference Array

Instead of updating each element directly, we use a helper array called **Difference Array (DA)**.

### ✅ How it Works:

- Create `DA[]` of size **(N + 1)**
- For each query `(l, r, x)`:
  - `DA[l] += x`
  - `DA[r + 1] -= x`

This takes **O(1)** time per update!

### ✨ Why it Works?

It creates "boundaries" of where the value `x` starts and stops. Later, by taking a prefix sum, we recover the actual array.

---

### 🔁 Building Final Array

After all updates, calculate prefix sum of `DA[]` to get the final result.

---

### 🧠 Example (in TypeScript)

```ts
let N = 5;
let DA = Array(N + 1).fill(0);
let queries = [
  [1, 3, 2],
  [2, 4, 3],
];

for (let [l, r, x] of queries) {
  DA[l] += x;
  DA[r + 1] -= x;
}

// Compute final array
let final = Array(N).fill(0);
final[0] = DA[0];
for (let i = 1; i < N; i++) {
  final[i] = final[i - 1] + DA[i];
}
console.log(final); // [0, 2, 5, 5, 3]
```

---

## ✅ Pros & ❌ Cons

### ✅ Pros

- 🔁 Constant time updates
- ⏱️ Efficient for large number of updates
- 💡 Easy to implement
- 📦 No need to access the array in between updates

### ❌ Cons

- ⚠️ Not suitable if frequent `get` queries are needed between updates
- 🐌 Prefix sum is required after all updates (O(N))

---

## 💡 When to Use

Use Difference Array Technique when:

- You have many **range updates** 🚀
- You **don’t** need intermediate results
- You want **fast and efficient** processing of updates
