        /*$stockSummary = DistributionRepresentativeStock::with('product')

        ->where('representative_session_id', $request->user_session)

        ->select('product_id')

        ->selectRaw('SUM(product_quantity) as total_quantity')

        ->groupBy('product_id')

        ->having('total_quantity','>',0)

        ->get();*/