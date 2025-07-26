```js
Swal.fire({
            title: 'Warning',
            text: 'message',
            icon: 'warning',
            showCancelButton: false,
            confirmButtonColor: '#3085d6',
            confirmButtonText: 'Ok'
        });
```

```js
const workIdResult = await Swal.fire({
            title: 'Your Work ID',
            input: "text",
            inputPlaceholder: "Enter Work ID",
            icon: 'question',
            showCancelButton: true,
            cancelButtonColor: '#da2a4f',
            confirmButtonColor: '#3085d6',
            confirmButtonText: 'Ok',
            didOpen: () => {
                const inputElement = Swal.getInput();
                inputElement.classList.add('work-id-input');
            },
            inputValidator: (value) => {
                return new Promise((resolve) => {
                    if (value !== "") {
                        resolve();
                    } else {
                        resolve("to continue please enter your Work ID");
                    }
                });
            }
        });
        
if (workIdResult.isConfirmed) {}
```