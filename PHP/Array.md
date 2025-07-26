

Absolutely Akila! Here's a **complete `.md` formatted reference** for **PHP array operations and functions**, perfect for your **Obsidian notes**.

---

````markdown
# 📚 PHP Array Operations & Functions Cheat Sheet

Everything you need to know about working with arrays in PHP.

---

## 🧱 Creating Arrays

```php
$arr1 = array(1, 2, 3);
$arr2 = [1, 2, 3];             // Short syntax

$assoc = [
  "name" => "Akila",
  "age" => 30
];

$nested = [
  "user" => [
    "name" => "Akila",
    "roles" => ["admin", "editor"]
  ]
];
````

---

## 🔎 Accessing & Modifying

```php
$arr[0];               // Access element
$assoc["name"];        // Access by key

$arr[1] = 10;          // Modify value
$assoc["age"] = 31;
```

---

## ➕ Add / Remove Elements

```php
$arr[] = 4;                        // Append
array_push($arr, 5);              // Append
array_unshift($arr, 0);           // Add to beginning

array_pop($arr);                  // Remove last
array_shift($arr);                // Remove first
unset($arr[2]);                   // Remove specific index/key
```

---

## 🔄 Looping Arrays

```php
foreach ($arr as $item) {
  echo $item;
}

foreach ($assoc as $key => $value) {
  echo "$key: $value";
}
```

---

## 📏 Count & Size

```php
count($arr);
sizeof($arr);
```

---

## 📐 Sort Functions

```php
sort($arr);               // Ascending, reindex
rsort($arr);              // Descending
asort($assoc);            // Sort by value, preserve keys
ksort($assoc);            // Sort by keys
arsort($assoc);           // Descending by value
krsort($assoc);           // Descending by key
```

---

## 🔍 Search & Check

```php
in_array("apple", $arr);          // true/false
array_search("apple", $arr);      // index or false

isset($arr[2]);                   // Check if exists
array_key_exists("name", $assoc);
```

---

## 🧰 Useful Array Functions

```php
array_keys($assoc);       // ["name", "age"]
array_values($assoc);     // ["Akila", 30]
array_merge($a1, $a2);    // Merge arrays
array_diff($a1, $a2);     // Values in a1 but not in a2
array_intersect($a1, $a2); // Common values

array_slice($arr, 1, 2);   // Extract a portion
array_splice($arr, 1, 2);  // Remove and optionally replace

array_unique($arr);       // Remove duplicates
array_reverse($arr);      // Reverse order
array_filter($arr);       // Remove empty/falsy
array_map(fn($x) => $x * 2, $arr); // Apply function
array_reduce($arr, fn($carry, $item) => $carry + $item);
```

---

## 🧪 Type & Structure

```php
is_array($arr);                    // Check if array
```

---

## 🔀 Combine & Chunk

```php
array_combine(["a", "b"], [1, 2]); // ['a' => 1, 'b' => 2]
array_chunk($arr, 2);             // Split into chunks
```

---

## 🔢 Range & Fill

```php
range(1, 5);                      // [1, 2, 3, 4, 5]
array_fill(0, 5, 'x');           // ['x', 'x', 'x', 'x', 'x']
```

---

## 🔄 Array Destructuring (PHP 7.1+)

```php
[$a, $b] = [1, 2];
// $a = 1, $b = 2
```

---

## 🧑‍💻 Example

```php
$students = [
  ["name" => "Akila", "score" => 85],
  ["name" => "Nimal", "score" => 90]
];

$scores = array_column($students, "score"); // [85, 90]
$total = array_sum($scores);               // 175
$average = $total / count($scores);        // 87.5
```

---

## 📌 Common Functions Quick Reference

|Function|Description|
|---|---|
|`array_push()`|Add to end|
|`array_pop()`|Remove from end|
|`array_shift()`|Remove first element|
|`array_unshift()`|Add to beginning|
|`array_merge()`|Merge arrays|
|`array_diff()`|Diff between arrays|
|`array_intersect()`|Common elements|
|`array_map()`|Apply callback to all elements|
|`array_filter()`|Filter with callback or truthy|
|`array_reduce()`|Reduce to single value|
|`array_key_exists()`|Check if key exists|
|`in_array()`|Check if value exists|

---

## 📎 Tip

✅ Use `print_r($array)` or `var_dump($array)` for debugging  
✅ Arrays can be used as stacks, queues, lists, dictionaries, trees, etc.

🧩 Official Docs: [https://www.php.net/manual/en/ref.array.php](https://www.php.net/manual/en/ref.array.php)

```

---

Would you like this exported as a `.md` file too? Or bundled together with the previous ones?
```