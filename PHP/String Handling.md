
---

````markdown
# 📘 PHP String Handling Cheat Sheet

A complete reference for working with strings in PHP.

---

## 🔤 Basics

```php
$name = "Akila";

// Double quotes parse variables
echo "Hello $name"; // Hello Akila

// Single quotes don't parse variables
echo 'Hello $name'; // Hello $name
````

---

## 📏 String Length & Access

```php
$str = "Hello";

echo strlen($str);  // 5
echo $str[1];       // e
```

---

## 🔁 Concatenation

```php
$first = "Hello";
$second = "World";

echo $first . " " . $second; // Hello World
```

---

## 📚 Common String Functions

### 🔍 Search

```php
strpos($haystack, $needle);
stripos($haystack, $needle);    // Case-insensitive

strrpos($haystack, $needle);
strripos($haystack, $needle);

str_contains($string, $substring);   // PHP 8+
str_starts_with($string, $prefix);  // PHP 8+
str_ends_with($string, $suffix);    // PHP 8+
```

### ✂️ Substrings

```php
substr($string, $start, $length);
strstr($string, $search);
strchr($string, $search);  // Alias of strstr
```

### 🧽 Trimming

```php
trim($string);
ltrim($string);
rtrim($string);
```

### 🔤 Case Conversion

```php
strtoupper($str);
strtolower($str);
ucfirst($str);
lcfirst($str);
ucwords($str);
```

### 🔁 Replace

```php
str_replace($search, $replace, $subject);
str_ireplace($search, $replace, $subject); // Case-insensitive

preg_replace('/pattern/', 'replacement', $subject); // Regex
```

### ✨ Formatting

```php
sprintf("Name: %s, Age: %d", "Akila", 30);
printf("Total: %.2f", 99.456); // Total: 99.46
```

---

## 🔢 Convert Between Array & String

### ➡️ Explode (String → Array)

```php
explode(",", "apple,banana,orange");
// ['apple', 'banana', 'orange']
```

### ⬅️ Implode (Array → String)

```php
implode("-", ['apple', 'banana', 'orange']);
// apple-banana-orange
```

---

## 🔄 Reverse & Repeat

```php
strrev("hello");        // olleh
str_repeat("ha", 3);    // hahaha
```

---

## 🔤 HTML & Entities

```php
htmlspecialchars("<b>bold</b>");  // &lt;b&gt;bold&lt;/b&gt;
html_entity_decode($string);
strip_tags($html);               // Remove all HTML tags
```

---

## 📐 Padding & Wrapping

```php
str_pad("42", 5, "0", STR_PAD_LEFT);   // 00042
wordwrap($text, 20, "<br>");           // Wrap text
```

---

## 🧮 Comparison

```php
strcmp($str1, $str2);
strcasecmp($str1, $str2);     // Case-insensitive
strnatcmp($a, $b);            // Natural order
```

---

## 🧪 Regex (preg_*)

```php
preg_match('/\d+/', $str, $matches);
preg_match_all('/[a-z]+/', $str, $matches);
preg_replace('/[0-9]/', '*', $str);
preg_split('/[\s,]+/', "a, b c"); // ["a", "b", "c"]
```

---

## 🌐 Multibyte (UTF-8 Safe)

```php
mb_strlen($str);
mb_strpos($str, $substr);
mb_substr($str, $start, $length);
mb_strtolower($str);
```

---

## 🛠 Misc Utilities

```php
addslashes("O'Reilly");     // O\'Reilly
stripslashes("O\\'Reilly"); // O'Reilly

number_format(1234567.89, 2, '.', ','); // 1,234,567.89
chunk_split("123456789", 3, "-");       // 123-456-789-
```

---

## 🧑‍💻 Example Use

```php
$name = " Akila Madusanka ";
$clean = trim($name);
$upper = strtoupper($clean);
$final = str_replace(" ", "_", $upper);  // AKILA_MADUSANKA
```
