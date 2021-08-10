# FlowDiMetrics
select PurchaseOrder.ORIGINALDOCUMENT,
Address_ForPurchaseOrder.COMPANY,
Address_ForPurchaseOrder.CODE,
PurchaseOrder_LineItem_Forecast.REFERENCENUMBER,
PurchaseOrder_LineItem_Forecast.SHIPDATE
from PurchaseOrder with(nolock)
left join PurchaseOrder_Address with(nolock) on PurchaseOrder.ID= PurchaseOrder_Address.PURCHASEORDER_ID
left join Address_ForPurchaseOrder with(nolock) on PurchaseOrder_Address.ADDRESS_ID=Address_ForPurchaseOrder.ID
left join PurchaseOrder_LineItem with(nolock) on PurchaseOrder.ID= PurchaseOrder_LineItem.PURCHASEORDER_ID
left join PurchaseOrder_LineItem_Forecast with(nolock) on PurchaseOrder_LineItem.ID= PurchaseOrder_LineItem_Forecast.LINEITEM_ID
where PurchaseOrder.ID='441AA373-8BA6-474A-A651-E93E1900256B'
