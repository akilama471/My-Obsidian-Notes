

> [!NOTE] Split String using some special charcter
> let timeRange = "1755-2358";
> timeRange.split('-');
> 


> [!NOTE] Replace string 
> 
```js
let time = "23:59"; 
let newTime = time.replace(":", ""); // Remove First find ":"
let newTime = time.replace(/:/g, ""); // Regular Expression Remove all instance of ":" 
let update_url = "{{ route('MemberController.update',':slug',) }}";
let _update_url = update_url.replace(':slug', memberID);
```
