# jQuery Select2 Event Listeners

## General Events
| Event Name         | Description                                                        |
| ------------------ | ------------------------------------------------------------------ |
| `select2:open`     | Triggered when the dropdown opens.                                 |
| `select2:close`    | Triggered when the dropdown closes.                                |
| `select2:select`   | Triggered when an option is selected.                              |
| `select2:unselect` | Triggered when an option is unselected (only for multiple select). |
| `select2:clear`    | Triggered when the selection is cleared.                           |

## Data Events
| Event Name            | Description                                                              |
| --------------------- | ------------------------------------------------------------------------ |
| `select2:selecting`   | Triggered before an option is selected. Allows preventing selection.     |
| `select2:unselecting` | Triggered before an option is unselected. Allows preventing unselection. |
| `select2:clearing`    | Triggered before clearing the selection. Allows preventing clearing.     |

## Loading Events
| Event Name        | Description |
|------------------|-------------|
| `select2:loading` | Triggered when results are loading (useful for AJAX). |
| `select2:loaded`  | Triggered when results have been loaded (useful for AJAX). |

## Searching Events
| Event Name        | Description |
|------------------|-------------|
| `select2:opening` | Triggered before the dropdown opens. Allows preventing opening. |
| `select2:closing` | Triggered before the dropdown closes. Allows preventing closing. |
| `select2:search`  | Triggered when a search is performed. |
| `select2:results` | Triggered when search results are updated. |

---

## Example Usage

```javascript
$('#mySelect').select2();

// Listening for events
$('#mySelect').on('select2:open', function (e) {
    console.log('Dropdown opened');
});

$('#mySelect').on('select2:close', function (e) {
    console.log('Dropdown closed');
});

$('#mySelect').on('select2:select', function (e) {
    console.log('Option selected: ', e.params.data);
});

$('#mySelect').on('select2:unselect', function (e) {
    console.log('Option unselected: ', e.params.data);
});

$('#mySelect').on('select2:search', function (e) {
    console.log('Searching...');
});
