---
title: Record Purchases with Purchase Invoices  (contains video)
description: Describes how to purchase inventory, non-inventory items, or resources by creating and posting purchase invoices or orders.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: procurement
ms.search.form: 50 ,51, 53, 56, 146
ms.date: 09/07/2021
ms.author: edupont

---
# Record Purchases with Purchase Invoices

You create a purchase invoice or purchase order to record the cost of purchases and to track accounts payable. If you need to control an inventory, purchase invoices and purchase orders are also used to dynamically update inventory levels so that you can minimize your inventory costs and provide better customer service. The purchasing costs, including service expenses, and inventory values that result from posting purchase invoices or orders contribute to profit figures and other financial KPIs on your Role Center.

## Create purchase invoices

In addition to buying physical items (**Inventory** item type), which affect inventory valuation, you can purchase services represented by time units. You can do this either with the **Service** item type or with the **Resource** line type.

When you receive the inventory items or when the purchased service is completed, you post the purchase invoice or order to update inventory and financial records and to activate payment to the vendor according to the payment terms. For more information, see [Posting Purchases](ui-post-purchases.md) and [Making Payments](payables-make-payments.md).

> [!CAUTION]  
> Do not post a purchase invoice for physical items until you receive the items and know the final cost of the purchase, including any additional charges. Otherwise, your inventory value and profit figures may be skewed.

### To create a purchase invoice

The following describes how to create a purchase invoice. The steps are similar for a purchase order. The main difference is that purchase orders have additional fields and actions for physical handling of items.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2. In the **Vendor** field, enter the name of an existing vendor.

    Other fields on the **Purchase Invoice** page are now filled with the standard information of the selected vendor. If the vendor is not registered, then follow these steps:

    1. In the **Vendor** field, enter the name of the new vendor.
    2. In the dialog box about registering the new vendor, choose the **Yes** button.
    3. For more on how to fill in the vendor card, see [Register New Vendors](purchasing-how-register-new-vendors.md).  
    4. When you have completed the vendor card, choose the **OK** button to return to the **Purchase Invoice** page.

3. Fill in the remaining fields on the **Purchase Invoice** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    You are now ready to fill in the purchase invoice lines with items or resources that you have purchased from the vendor.

    > [!NOTE]  
    > If you have set up recurring purchase lines for the vendor, such as a monthly replenishment order, then you can insert these lines on the invoice by choosing the **Get Recurring Purchase Lines** action.
4. On the **Lines** FastTab, in the **Item No.** field, enter the number of an inventory item or service.
5. In the **Quantity** field, enter the number of items to be purchased.

    The **Line Amount** field is updated to show the value in the **Direct Unit Cost** field multiplied by the value in the **Quantity** field.

    The price and line amount are shown with or without sales tax depending on what you selected in the **Prices Including Tax** field on the vendor card.

    The totals fields under the lines are automatically updated as you create or modify lines to display the amounts that will be posted to the ledgers.

6. In the **Invoice Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field at the bottom of the invoice.

    > [!NOTE]  
    > If you have set up invoice discounts for the vendor, then the specified percentage value is automatically inserted in the **Vendor Invoice Discount %** field if the criteria are met, and the related amount is inserted in the **Invoice Discount Amount** field.
7. When you receive the purchased items or services, choose **Post**.

The purchase is now reflected in inventory, resource ledgers, and financial records, and the vendor payment is activated. The purchase invoice is removed from the list of purchase invoices and replaced with a new document in the list of posted purchase invoices.  

> [!NOTE]
> In rare cases, the posted amounts may deviate from what is displayed in the totals fields. This is typically due to rounding calculations in relation to VAT or sales tax.
>
> To check the amounts that will actually be posted, you can use the **Statistics** page, which takes into account the rounding calculations. Also, if you choose the **Release** action, the totals fields will be updated to include rounding calculations.

## When to use purchase orders

You must use purchase orders if your purchasing process requires that you record partial receipts of an order quantity, for example, because the full quantity was not available at the vendor. If you sell items by delivering directly from your vendor to your customer, as a drop shipment, then you must also use purchase orders. For more information, see [Make Drop Shipments](sales-how-drop-shipment.md). In all other aspects, purchase orders work the same way as purchase invoices. The following procedure is based on a purchase invoice. The steps are similar for a purchase order.

<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE4b3tt?rel=0]

## Selling non-inventory items

The items on a purchase invoice can be of type **Inventory**, **Service**, **Resource** and **Non-Inventory** to specify if the item is a physical inventory unit, a labor time unit, or a physical unit that is not kept on inventory. For more information, see [Register New Items](inventory-how-register-new-items.md). The purchase invoice process is the same for all three item types.

> [!NOTE]
> With the **Resource** purchase line type, you can also purchase external resources, for example, to invoice a vendor for work delivered. For more information, see [Set Up Resources](projects-how-setup-resources.md).
>
> To use a purchased resource, you may need to set the resource's capacity and manually assign it to a job. Purchasing a resource will create a resource ledger entry, however, resource ledger entries are not tracked for quantity and value as, for example, items are. If quantity and value tracking is required, then consider using other line item types.

## Posted invoices

[!INCLUDE [posted-invoices](includes/posted-invoices.md)]

You can easily correct or cancel a posted purchase invoice before you pay the vendor. This is useful if you want to correct a typing mistake or if you want to change the purchase early in the order process. For more information, see [Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md). If you have already paid for items or services on the posted purchase invoice, then you must create a purchase credit memo to reverse the purchase. For more information, see [Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md).

[Open the **Posted Purchase Invoices** list](https://businesscentral.dynamics.com/?page=146) in [!INCLUDE [prod_short](includes/prod_short.md)].

## External document number

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## See Related Training at [Microsoft Learn](/learn/modules/processing-invoices-dynamics-365-business-central/index)

## See Also

[Purchasing](purchasing-manage-purchasing.md)  
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Set Up Resources](projects-how-setup-resources.md)  
[Posting Purchases](ui-post-purchases.md)  
[Request Quotes](purchasing-how-request-quotes.md)  
[Purchase Items for a Sale](purchasing-how-purchase-products-sale.md)  
[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Prepare Drop Shipments](sales-how-drop-shipment.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]