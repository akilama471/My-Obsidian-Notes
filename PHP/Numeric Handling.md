
Absolutely Akila! Here's a comprehensive `.md` formatted cheat sheet for **PHP numeric operations and methods**, ideal for your **Obsidian notes**:

---

````markdown
# 🔢 PHP Numeric Operations & Functions

Everything you need to know about working with numbers in PHP.

---

## 🧮 Basic Arithmetic

```php
$a = 10;
$b = 3;

$a + $b;   // Addition → 13
$a - $b;   // Subtraction → 7
$a * $b;   // Multiplication → 30
$a / $b;   // Division → 3.333...
$a % $b;   // Modulus (Remainder) → 1
$a ** $b;  // Exponentiation → 1000
````

---

## 📈 Increment / Decrement

```php
$x = 5;

$x++;  // Post-increment → returns 5, then $x = 6
++$x;  // Pre-increment  → $x = 7
$x--;  // Post-decrement → returns 7, then $x = 6
--$x;  // Pre-decrement  → $x = 5
```

---

## 🧪 Type Checking

```php
is_int($value);        // true if integer
is_float($value);      // true if float
is_numeric($value);    // true if numeric string or number
```

---

## 🔁 Type Casting

```php
$val = (int)"5";        // 5
$val = (float)"10.5";   // 10.5
$val = (string)123;     // "123"
```

---

## 📊 Rounding & Precision

```php
round(3.456, 2);       // 3.46 (Round to 2 decimal places)
floor(3.9);            // 3 (Round down)
ceil(3.1);             // 4 (Round up)
```

---

## 📉 Min / Max / Absolute

```php
min(4, 2, 8);          // 2
max(4, 2, 8);          // 8
abs(-100);             // 100
```

---

## 📐 Power & Roots

```php
pow(2, 3);             // 8 (2³)
sqrt(16);              // 4
```

---

## 🧮 Trigonometry (in radians)

```php
sin(deg2rad(90));      // 1
cos(deg2rad(180));     // -1
tan(deg2rad(45));      // 1

rad2deg(pi());         // 180
```

---

## 💲 Formatting Numbers

```php
number_format(1234.567, 2, '.', ',');
// Output: "1,234.57"

number_format(1000); 
// Output: "1,000"
```

---

## 🔀 Random Numbers

```php
rand();               // Random integer
rand(1, 100);         // Between 1 and 100

mt_rand(1, 100);      // Faster and better random
random_int(1, 100);   // Cryptographically secure (PHP 7+)
```

---

## 💹 Base Conversion

```php
decbin(10);    // "1010"
decoct(10);    // "12"
dechex(10);    // "a"

bindec("1010"); // 10
octdec("12");   // 10
hexdec("a");    // 10

base_convert("1010", 2, 16); // "a"
```

---

## 🧠 Constants

```php
PHP_INT_MAX;     // Largest supported integer
PHP_INT_MIN;     // Smallest supported integer
PHP_FLOAT_MAX;   // Largest float
PHP_FLOAT_MIN;   // Smallest float
```

---

## 🧰 Math Functions (Misc)

```php
pi();                   // 3.1415926535898
fmod(7.5, 2.5);         // 2.5 (Float modulus)
log(10);                // Natural log
log10(100);             // Base-10 log → 2
exp(1);                 // e^1 → 2.718281828459

min([3,5,1,9]);         // 1
max([3,5,1,9]);         // 9
```

---

## 🧪 Useful Checks

```php
is_nan($val);           // Check if Not-a-Number
is_finite($val);
is_infinite($val);
```

---

## 🧑‍💻 Example

```php
$price = 12345.6789;
$discount = 0.15;

$final = $price - ($price * $discount);
$formatted = number_format($final, 2);  // 10493.83
```

---

## 📎 Tip

📌 Use `declare(strict_types=1);` at the top of files for strict typing with numeric functions. 📌 For crypto-safe random numbers, always use `random_int()` instead of `rand()`.

🧩 Reference: [https://www.php.net/manual/en/ref.math.php](https://www.php.net/manual/en/ref.math.php)

```

---

Would you like this exported as a downloadable `.md` file as well?
```