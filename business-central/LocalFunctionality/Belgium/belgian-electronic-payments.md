---
title: Belgian Electronic Payments
description: In the electronic banking module in the Belgian version of Business Central, you can make domestic, international, SEPA, and non-Euro SEPA electronic payments.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords:
ms.search.form: 2000006
ms.date: 04/01/2021
ms.author: edupont

---
# Belgian Electronic Payments

In the Belgian version of [!INCLUDE[prod_short](../../includes/prod_short.md)], you can the following types of electronic payments:  

|Electronic payment|Description|  
|------------------------|---------------------------------------|  
|Domestic|These payments are in the local currency (LCY) and are processed by a local financial institution for beneficiaries who have accounts that have a local financial institution. The validity of the bank account numbers will be verified by [!INCLUDE[prod_short](../../includes/prod_short.md)].|  
|International|These payments are either in foreign currencies or in LCY and are processed by a local financial institution for beneficiaries who have accounts that have foreign financial institutions. The validity of the bank account numbers will not be verified by [!INCLUDE[prod_short](../../includes/prod_short.md)].|  
|SEPA|These payments are in euro and are processed in countries/regions that accept SEPA payments. The validity of the bank account numbers will be verified by [!INCLUDE[prod_short](../../includes/prod_short.md)].|  
|Non-Euro SEPA|These payments are in currency other than euro and made to a country/region outside the European Economic Association (EEA). The validity of the bank account numbers will be verified by [!INCLUDE[prod_short](../../includes/prod_short.md)].|  

Because the standard for electronic payments is different for countries/regions, electronic payments created in the Belgian version of [!INCLUDE[prod_short](../../includes/prod_short.md)] can only be processed by financial institutions in Belgium. For international payments, the local financial institutions will then have to process the payment with the foreign institutions.  

> [!NOTE]  
> Credit memos cannot be processed separately because payments must not have a negative balance. To process a credit memo, the credit memo must be added to one or more invoices by summarizing payments.  

Before you can make electronic payments, you must set up use electronic banking. For more information, see [Setup](belgian-electronic-banking.md#setup). You must also specify the relevant export protocols. For more information, see [Set Up Export Protocols](how-to-set-up-export-protocols.md).  

## Activate SEPA Payments in the Belgian Version

[!INCLUDE [activate-sepa-payments](../includes/BENL/activate-sepa-payments.md)]

You can now make SEPA payments. For more information, see [Exporting Payments to a Bank File](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file). If you do not use the AC Banking 365 capability, you can export payment journal lines to a file. For more information, see [Export Payment Files](how-to-print-payment-files.md).  

## File Non-Euro SEPA Payments

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can file non-euro SEPA payments with the bank. This is useful when you make payments to other countries that do not use SEPA and for currencies other than the euro.  

Before you can file a non-euro SEPA payment you must complete the following administration tasks:  

- Set up a new export protocol for a non-euro SEPA.  
- In the **Country/Region** table, clear the **SEPA Allowed** field for each country that belongs to the EEA zone.  
- In the **General Ledger Setup** page, verify that the **Currency Euro** field is blank, and that the **SEPA Non-Euro Export** field is selected.  
- Verify that the vendor's **Preferred Bank Account** field in the **Vendor** table contains the IBAN and SWIFT code.  

## To file a non-euro SEPA payment  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **File Non Euro SEPA Payments**, and then choose the related link.  
2. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Specify the general journal template for the non-euro SEPA payment report.|  
    |**Journal Batch**|Specify the general journal batch for the non-euro SEPA payment report.|  
    |**Post General Journal Lines**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**Include Dimensions**|Enter the dimensions that you want to include in the non-euro SEPA payment report. The option is available only if the **Summarize Gen. Jnl. Lines** field on the **Electronic Banking Setup** page is selected.|  
    |**Execution Date**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**File Name**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  

## Correcting Payment Lines

You must correct all errors before you can post the electronic payment lines. You can correct payment lines in the following ways.  

|Correction|Description|  
|----------------|---------------------------------------|  
|Add a payment journal line|If the payment journal already contains many lines and you want to add an additional line, you can enter the journal line manually. For example, if you want to reimburse a credit memo to a customer. These types of customer payments are not suggested automatically by the **Suggest Vendor Payments** batch job.|  
|Edit a payment journal line|If you have not assigned a bank account to the payment journal or if you have not specified a preferred bank account on the Vendor card, you will have to manually enter this information on each journal line before posting the journal. If you specify a bank account for a vendor, the bank account will be copied to all payment journal lines for that vendor. For more information, see [Setup](belgian-electronic-banking.md#setup).|  
|Delete a payment journal line|The **Suggest Vendor Payments** batch job creates payment suggestions for all vendors matching the specified criteria. If you want to prevent payment for a specific vendor ledger entry or vendor, you can delete the corresponding journal lines.|  


## See Also

[Belgium Local Functionality](belgium-local-functionality.md)  
[Belgian Electronic Banking](belgian-electronic-banking.md)  
[Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)  
[Suggest Vendor Payments](../../payables-how-suggest-vendor-payments.md)  
[Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)  
[Test Electronic Payments](how-to-test-electronic-payments.md)  
[Print Payment Files](how-to-print-payment-files.md)  
