---
Title: "Factoring"
Author: Autocont
Ms. custom: on
Ms date: 04/13/2018
reviewer: Ms.
Ms. suite:
Ms. _pltfrm tgt:
Ms. topic: article
MS Sales: dynamics-nav-2018
Ms. translationtype: Human Translation
Ms. sourcegitcommit:
Ms. openlocfilehash:
Ms. contentlocale: cs-cz
Ms. lasthandoff: 03/27/2018
---

# ## <a name = "ac-fp-factoring" > </a> Factoring
The Factoring area extends financial management system Microsoft Dynamics NAV by the possibility of registration and accounting of the assignment of receivables and the creation of factoring contracts.

# # Set

### General
After you import the objects, you must complete the setup of the factoring. Basic Setup is done in the/proFINACE/Factoring.
For correct function of the factoring, you must perform the following steps:
In the chart of accounts to establish financial accounts for the monitoring of assigned claims and cost and revenue accounts for transfer of factoring (optional)
* Establish posting groups for factoring
* Assign posting groups for factoring
* Set up a billing factoring
* Create a template for a factoring contract

### Establishment of accounts in the chart of accounts
Update the chart of accounts shall be made in the area of Finance/Administration/Finance/accounts. In the chart of accounts, you can specify the g/l accounts needed for posting of factoring.

### Establishment of posting groups for factoring
The posting groups are set up in the area/administration/application settings/financial management/inventory posting group – customer posting groups. 
In the customer posting groups, you can specify the posting group that will be used for posting of factoring.

### Set the spare customer posting groups
Form of compensation the customer posting group located on the form the customer posting group on the Navigation option compensation.
The combination of field values by setting the Replacement customer posting group and customer posting groups define the number of the account that will be charged in connection with the factoring.

### Set the factoring
Form of factoring is in the region/proFINANCE/Factoring-factoring Setting.
On the form, setting the factoring is necessary to make the following settings:
The Úèto skupina faktoringů: posting group used when posting the factoring receivables
The Offset of the costs: account receivable is posted for the customer
* Revenue-offset: account to which the program posts the yield of factoring
The VAT product posting group: Here you must set up VAT product posting group, which in combination with the VAT business posting group from the customer-factor represents the posting without VAT
* Charged to the original item: Select YES to further monitor the claim under the original customer on the off balance sheet accounts
The transfer posting group and Bal. transfer: off-balance sheet accounts, which will continue to monitor the claim to the original customer
* Faktoringů: Sequence Numbers, which will be faktoringy numbered

### Create the document factoring
It is possible to define templates for the conversion of factoring contracts into Microsoft Word documents.
We will create a document on the factoring using the create document factoring ** tab ** Navigation **.
On the ** ** select Options then in the * Word * Template * the appropriate template, by which we want to generate the document.

## Use

### The acquisition document factoring
The form of the document is located in the area of factoring/proFINANCE/Factoring/overview faktoringů. To the document, you must fill in the sell-to customer number ** ** (Integer factor) and posting date.
Specific accounts receivable/payable, which are to be surrendered, can be selected by using the fields type items ** and ** ** item number. If this is a regression, factoring, factor may claim/commitment to return the field must be selected * Regression factoring ** on the document line.

# Posted by factoring
Before you post a document, the document must be issued by factoring-** Issue ** on the actions tab. (Ctrl + F9). Post the document is performed via the * Posting * (F9). After posting a document * * Posted *, the factoring can be found in the area//Factoring/proFINANCE Overview posted faktoringů.
The posted document lines factoring are divided into three tabs:
* Accounts receivable – ceded items
* Factoring receivables – new customer ledger entries to faktorovi
Payment – the payment of the item type, which offset the factoring receivables
The posting of factoring are closed the original customer/vendor entries and to faktorovi are posted new claims. Financial accounting is intended ** Factoring * posting group, from the setup of factoring (in this case — FACTORING). 
If it is turned on in the settings of the factoring ** charged to the original item **, there will be a new customer, customer/vendor/supplier of the item. This allows you to monitor the balance of the original customers/suppliers including referred to the documents. Financial accounting is intended ** of ** posting group from the settings of the factoring (in this case, PŘEÚČTO. F.). In the settings of the customer posting group of the refund would be for this posting group the account should be set to podrozvahový. Off balance sheet item is closed at the time of the conclusion of the factoring of receivables.
Financial accounting, depending on the system settings may have the following impact on the chart of accounts (for example, the assignment of one item with the přeúčtováním on the podrozvahový account).

### Return factoring receivables
If this is a regression, factoring, factor may claim return voucher must be posted with a checked box ** factoring * on the Regression line of the document.
For recovery, you must select an action on the posted factoring ** factoring * claim * to return.
After this command, the system will subtract a newly created item and will charge it factoring back to the customer/vendor.

## <a name = "see-also" > </a>See Also   

[AC Financial Pack](ac-fp-financial-pack.md)















