
You can find the complete documentation for **AdminLTE Bootstrap Modal** along with available functions in the official documentation here:  
🔗 [AdminLTE Documentation](https://adminlte.io/docs/3.1/)

### **Available Modal Functions**

1. **Show Modal**
    
    ```javascript
    $('#myModal').modal('show');
    ```
    
2. **Hide Modal**
    
    ```javascript
    $('#myModal').modal('hide');
    ```
    
3. **Toggle Modal**
    
    ```javascript
    $('#myModal').modal('toggle');
    ```
    
4. **Dispose Modal (Remove event listeners)**
    
    ```javascript
    $('#myModal').modal('dispose');
    ```
    
5. **Handle Modal Events**
    
    ```javascript
    $('#myModal').on('shown.bs.modal', function () {
        console.log('Modal is fully visible');
    });
    ```


To detect when a Bootstrap modal (AdminLTE uses Bootstrap modals) is hidden, use the **`hidden.bs.modal`** event. This event is triggered after the modal has been fully hidden.

### **Example Code**

```javascript
$('#myModal').on('hidden.bs.modal', function () {
    console.log('Modal has been completely hidden.');
});
```

### **Explanation**

- `hidden.bs.modal`: Fires when the modal is completely hidden (after the animation finishes).
- The callback function runs when the event occurs.

### **Other Related Events**

1. **Before Modal Hides** (`hide.bs.modal`)
    
    ```javascript
    $('#myModal').on('hide.bs.modal', function () {
        console.log('Modal is about to be hidden.');
    });
    ```
    
2. **When Modal is Shown** (`shown.bs.modal`)
    
    ```javascript
    $('#myModal').on('shown.bs.modal', function () {
        console.log('Modal is fully visible.');
    });
    ```