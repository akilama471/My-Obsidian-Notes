Sure! Here's a **complete and categorized list** of **JavaScript Array methods**, with **short explanations** for each.

---

## 🟢 **Creating & Checking**

|Method|Description|
|---|---|
|`Array.of(...)`|Creates a new array from arguments|
|`Array.from(iterable)`|Creates an array from iterable (like string, Set, etc.)|
|`Array.isArray(arr)`|Checks if a value is an array|

---

## 🔵 **Adding / Removing Elements**

| Method                                 | Description                              |
| -------------------------------------- | ---------------------------------------- |
| `push(item)`                           | Adds item(s) to the **end**              |
| `pop()`                                | Removes and returns the **last** item    |
| `unshift(item)`                        | Adds item(s) to the **beginning**        |
| `shift()`                              | Removes and returns the **first** item   |
| `splice(start, deleteCount, ...items)` | Add/remove items at any position         |
| `slice(start, end)`                    | Returns a shallow copy (non-destructive) |
| `fill(value, start, end)`              | Fills elements with a static value       |
| `copyWithin(target, start, end)`       | Copies part of array within itself       |

---

## 🟣 **Searching & Checking**

|Method|Description|
|---|---|
|`includes(value)`|Checks if array includes a value|
|`indexOf(value)`|Returns first index of value (or -1)|
|`lastIndexOf(value)`|Returns last index of value|
|`find(callback)`|Returns first matching element|
|`findIndex(callback)`|Returns index of first match|
|`some(callback)`|Returns `true` if **any** match|
|`every(callback)`|Returns `true` if **all** match|

---

## 🟠 **Iteration / Looping**

|Method|Description|
|---|---|
|`forEach(callback)`|Loops over each element (no return)|
|`map(callback)`|Transforms each item, returns new array|
|`filter(callback)`|Returns array of items that match|
|`reduce(callback, initial)`|Reduces array to a single value|
|`reduceRight(...)`|Like `reduce`, but from right to left|
|`flat(depth)`|Flattens nested arrays|
|`flatMap(callback)`|Like map + flat(1)|
|`entries()`|Returns array iterator of [index, value]|
|`keys()`|Returns array iterator of keys|
|`values()`|Returns array iterator of values|

---

## 🟡 **Sorting & Reversing**

|Method|Description|
|---|---|
|`sort(compareFn)`|Sorts the array in-place|
|`reverse()`|Reverses array in-place|

---

## 🔴 **Joining & Combining**

|Method|Description|
|---|---|
|`join(separator)`|Joins elements into string|
|`toString()`|Converts array to string|
|`concat(...arrays)`|Combines arrays into new array|
|`toLocaleString()`|Locale-specific string of array|

---

## 🟤 **Other Useful Tools**

|Method|Description|
|---|---|
|`length`|Property: number of elements|
|`at(index)`|Gets item at index (supports negative)|

---

## 🧪 Bonus: Typed Arrays (Advanced)

For binary or performance-critical work: `Uint8Array`, `Float32Array`, etc. (These are not regular arrays but behave similarly.)

---

### 🔁 Want a printable version or Obsidian-friendly markdown table?

Let me know — I’ll format it perfectly for your use case.

Would you like **real-world examples** of commonly used methods too?