---
title: Electronic Invoicing [MX]
description: Business Central supports CFDI so that you can export sales and service invoices and credit memos as electronic documents with the required digital signature.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 10458, 10459, 27001, 27002,27010,27011,27011, 27012, 27013,27014,27015
ms.date: 11/25/2021
ms.author: edupont

---
# Electronic Invoicing in the Mexican Version

Mexican companies must be able to send invoices electronically as Comprobante Fiscal Digital por Internet (CFDI) files. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports CFDI so that you can export sales and service invoices and credit memos as electronic documents that have the required digital signature.  

The CFDI file is an XML file that contains:  

- Name of issuing company.  
- Fiscal address of issuing company.  
- Tax scheme of the issuing company.  
- Federal tax registration number (RFC) of issuing company.  
- RFC of the receiving company.  
- Quantity and description of the goods or services.  
- Unit price.  
- Tax amounts listed by tax type.  
- Currency code.  
- Customs location, which includes the date and number of the customs document, if the transaction is an import.  
- Digital stamp of the issuing company, which is assigned by the tax authorities (SAT).  
- Digital stamp of an authorized service provider, PAC, that you choose.  

> [!IMPORTANT]  
> You will be submitting the electronic invoices to a PAC, which is an authorized service provider appointed by the Mexican tax authorities (SAT).  

## Getting Started

Before you can use [!INCLUDE[prod_short](../../includes/prod_short.md)] for electronic invoicing, you must obtain the appropriate certification, digital stamp, and control numbers from the tax authorities. You must install the certificate on the computer where the CFDI files will be generated. For more information, see [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md). For information about SAT certificates and keys, see the [Servicio de Administracíon Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website.  

> [!TIP]
> Use the **Set up Mexican CFDI information** assisted setup guide to map information about your company and how you use [!INCLUDE [prod_short](../../includes/prod_short.md)] to the various fields in the CFDI files.

You also must specify the web services that you will use to communicate with the PAC in order to obtain digital stamps. For more information, see [Set Up PAC Web Services](how-to-set-up-pac-web-services.md).  

> [!IMPORTANT]  
> SAT has certified more than one PAC in Mexico, and you must obtain the appropriate information to communicate with the PAC of your choice.  

## Sending Electronic Invoices

When you have posted an invoice or credit memo, you can send it to your customer. But first you must obtain a digital stamp from a PAC. [!INCLUDE[prod_short](../../includes/prod_short.md)] communicates with the PAC through web services to request a stamp, and the document is automatically digitally signed by your company and the PAC.  

When you send an electronic invoice or credit memo to your customer, [!INCLUDE[prod_short](../../includes/prod_short.md)] uses the email address that you have specified on the **Company Information** page. The document is sent to the email address that you have specified on the **Customer Card** page for the bill-to customer on the invoice or credit memo. On the **General Ledger Setup** page, you also can choose to include the documents as PDF files in the email that is sent.  

> [!IMPORTANT]  
> The users who will send electronic invoices must be able to send mail using the Simple Mail Transfer Protocol (SMTP). Depending on the configuration in your company, you may have to grant explicit permissions to each relevant user and computer.  

If you also want to print the documents, the documents will include a Quick Response (QR) bar code and other information that identifies the related electronic invoice. This information makes the printed document computer-readable and provides a link between the electronic document and the printed document.  

For more information, see [Generate Electronic Invoices](how-to-generate-electronic-invoices.md).  

## Communication Component

Technically, the [!INCLUDE[prod_short](../../includes/prod_short.md)] component for electronic invoicing deploys in a library assembly, Microsoft.Dynamics.NAV.MX.dll, which is included automatically with [!INCLUDE[prod_short](../../includes/prod_short.md)]. The component handles the communication with the PAC web services and also generates the QR codes that are included in the printed documents.  

When you generate an electronic document to request a stamp, [!INCLUDE[prod_short](../../includes/prod_short.md)] creates an XML document and sends it to the PAC for processing. The original XML document contains the same information as the original string field that is shown on the printed document. The original string includes the following information:  

- Document date  
- Document type  
- Payment terms  
- Name, address, and federal registration number of your company  
- Name, address, and federal registration number of the customer  
- Line amounts and quantities  

The PAC returns an XML document that has the original string, but this file also includes a section for the digital stamp. In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can export the XML files for documents that have a digital stamp and learn more about the data that goes into each XML element.  

## See Also

[Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
[Set Up PAC Web Services](how-to-set-up-pac-web-services.md)  
[Generate Electronic Invoices](how-to-generate-electronic-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]