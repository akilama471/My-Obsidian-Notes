	
> [!NOTE] Get all tr from table body
> $('#alocation_placeholder_3_datatable_body').find('tr').each(function() {}

```
$('#alocation_placeholder_3_datatable_body').find('tr').each(function() {
	let firstTdValue = $(this).find('td').first().text();
	let timeRange = $(this).closest('td').prev('td').text().trim();
	let timeParts = timeRange.split('-');
	let startTime = timeParts[0];
	let endTime = timeParts[1];
})
```
