
```HTML

<table id="PurchaseTable" data-order='[ 6, "asc" ]' data-page-length='25' class="table table-bordered table-striped table-sm">
                        <caption>Purchase List</caption>
                        <thead>
                            <tr>
                                <th>
                                    <div class="text-center">Action</div>
                                </th>
                                <th>
                                    <div class="text-center">Purchase Number</div>
                                </th>
                                <th>
                                    <div class="text-center">Supplier</div>
                                </th>
                                <th>
                                    <div class="text-center">Payment Status</div>
                                </th>
                                <th>
                                    <div class="text-center">Total</div>
                                </th>
                                <th>
                                    <div class="text-center">Due</div>
                                </th>
                                <th>
                                    <div class="text-center">Purchase Date</div>
                                </th>
                                <th>
                                    <div class="text-center">Location</div>
                                </th>
                            </tr>
                        </thead>
                        <tbody>
                        </tbody>
                    </table>```

```js
PurchaseTable = $("#PurchaseTable").DataTable({
                processing: true,
                serverSide: true,
                responsive: true,
                lengthChange: true,
                autoWidth: false,
                searching: false,
                columnDefs: [{
                    targets: [0,1,2,3,4,5,7],
                    orderable: false,
                    searchable: false
                }],
                ajax: {
                    url: "{{ route('PurchasesController.listPurchase') }}",
                    data: function(d) {
                        d.grn_number = $('#invoiceNumberFilter').val();
                        d.grn_supplier = $('#supplierSelector').val();
                        d.grn_user = $('#purchaseUserSelector').val();
                        d.grn_location = $('#purchaseLocationSelector').val();
                        d.pay_status = $('#paymentStatusSelector').val();
                        d.product_barcode = $('#productBarcode').val();
                        d.product_serial = $('#productSerial').val();
                        d.start_date = $('#invoiceDateRange').data('daterangepicker').startDate.format('YYYY-MM-DD');
                        d.end_date = $('#invoiceDateRange').data('daterangepicker').endDate.format('YYYY-MM-DD');
                    }
                },
                columns: [
                {data: 'purchase_action'},
				{data: 'purchase_numbere'},
				{data: 'purchase_supplier'},
				{data: 'purchase_status'},
				{data: 'purchase_total'},
				{data: 'purchase_due'},
				{data: 'purchase_date'},
				{data: 'purchase_location'},
                ],
                "initComplete": function() {
                    $cardOverlay.attr('hidden', true)
                }
            });```

```php
use Throwable;
use Yajra\DataTables\DataTables;

public function listPurchase(Request $request): JsonResponse
{
	$purchaseList = PurchaseIndex::where('company_id', Auth::user()->company_id)->where('status', 1);
	if ($request->has('grn_supplier') && $request->input('grn_supplier') != '-1') {
		$purchaseList->where('supplier_id', $request->input('grn_supplier'));
	}
	$purchaseList->orderBy('created_at', 'desc');
	
	return Datatables::of($purchaseList)
            ->addIndexColumn()
            ->addColumn('purchase_numbere', function ($row) {
                return $row->grn_number;
            })
            ->rawColumns(['purchase_action'])
            ->make();
    }
```