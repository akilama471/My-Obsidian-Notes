# jQuery Selectors Cheat Sheet

## Index-Based Selectors
| Selector  | Description |
|-----------|------------|
| `:eq(n)`  | Selects the element at **index `n`**. |
| `:gt(n)`  | Selects elements **greater than** index `n`. |
| `:lt(n)`  | Selects elements **less than** index `n`. |
| `:first`  | Selects the **first** element in a group. |
| `:last`   | Selects the **last** element in a group. |
| `:even`   | Selects elements at **even** indices (0, 2, 4, ...). |
| `:odd`    | Selects elements at **odd** indices (1, 3, 5, ...). |

---

## Form Selectors
| Selector        | Description |
|----------------|-------------|
| `:input`       | Selects all `<input>`, `<textarea>`, `<select>`, and `<button>`. |
| `:text`        | Selects `<input type="text">`. |
| `:password`    | Selects `<input type="password">`. |
| `:checkbox`    | Selects checkboxes (`<input type="checkbox">`). |
| `:radio`       | Selects radio buttons (`<input type="radio">`). |
| `:submit`      | Selects submit buttons (`<input type="submit">`). |
| `:reset`       | Selects reset buttons (`<input type="reset">`). |
| `:button`      | Selects buttons (`<button>` or `<input type="button">`). |
| `:file`        | Selects file inputs (`<input type="file">`). |
| `:image`       | Selects `<input type="image">`. |
| `:focus`       | Selects the currently **focused** element. |
| `:checked`     | Selects all **checked** checkboxes/radio buttons. |
| `:selected`    | Selects `<option>` elements that are **selected**. |
| `:disabled`    | Selects **disabled** elements. |
| `:enabled`     | Selects **enabled** elements. |

---

## Visibility Selectors
| Selector    | Description |
|------------|-------------|
| `:visible` | Selects elements that are **visible**. |
| `:hidden`  | Selects elements that are **hidden**. |

---

## Content-Based Selectors
| Selector            | Description |
|--------------------|-------------|
| `:contains("text")` | Selects elements that contain the specified **text**. |
| `:empty`           | Selects elements that have **no child elements** or text. |
| `:has(selector)`   | Selects elements that **contain** a specific child element. |
| `:parent`          | Selects elements that are **not empty** (contain child elements). |

---

## Attribute-Based Selectors
| Selector           | Description |
|-------------------|-------------|
| `[attr]`          | Selects elements that have the **attribute** `attr`. |
| `[attr="value"]`  | Selects elements where `attr` equals `"value"`. |
| `[attr!="value"]` | Selects elements where `attr` **is not** `"value"`. |
| `[attr^="value"]` | Selects elements where `attr` **starts with** `"value"`. |
| `[attr$="value"]` | Selects elements where `attr` **ends with** `"value"`. |
| `[attr*="value"]` | Selects elements where `attr` **contains** `"value"`. |

---

## Hierarchy-Based Selectors
| Selector              | Description |
|----------------------|-------------|
| `$("parent > child")` | Selects **direct** child elements. |
| `$("ancestor descendant")` | Selects **any descendant** inside the ancestor. |
| `$("prev + next")`  | Selects the **next sibling** element. |
| `$("prev ~ siblings")` | Selects all **siblings** after `prev`. |

---

## Examples

### 1️⃣ Select the 3rd `<li>` element in a list
```js
$("li:eq(2)").css("color", "red"); // (Index is 0-based)
```

### 2️⃣ Select all `<td>` except the first one in a row

```js
`$("tr td:gt(0)").css("background", "yellow");`
```
### 3️⃣ Select only checked checkboxes
```js
`$("input:checkbox:checked").val();`
```
### 4️⃣ Select all `div` elements containing the word "Hello"
```js
`$("div:contains('Hello')").css("border", "1px solid red");`
```

### 5️⃣ Select all input fields that are enabled
```js
`$("input:enabled").css("background", "lightblue");`
```

### **multiple selectors** together for more precise filtering.  
```js
`$("input:checkbox:checked:visible").val();`
```