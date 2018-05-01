---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Spa Services invoicing

Billing takes place at the standard spa services sales documents (Sales invoice, sales credit memo) and also on the sales of cash documents (Till Document, Till credit memo) that have been created in the framework of the Spa solution. For these documents are created and customized reports. For fast and convenience of users uses the functionality that allows you to preset certain information. 

## SETUP
### Standard sale codes
For invoicing spa services on sales documents it is necessary to establish **Standard sales codes**. This is a standard functionality that was within the Spa solution extended with the ability to work with spa services. 
For the use of sales spa services should be in the standard sales lines fill in the fields:
-	Type = Account
-	The type of spa services = selection of the following values
	- 	Add-on service
	- 	Curative stay
	- 	Accommodation
	- 	Catering
	- 	Service in the restaurant
	- 	Procedure
	- 	Laboratory
	- 	Nursing care
	- 	Fee
	- 	Phone
	- 	Wellness service
-	Sales code – this field can be filled in two ways:
	- 	A specific value depending on the type of service--then gets to the sales document. By selecting a specific service will also make up the number, description and product posting group.
	- 	An empty value – a specific service will pick up on the receipt, depending on the type of spa services

### Sale cash desk documents
**Checkout**  
Depending on the currencies should be based standard cash register in the management of Finance – Treasury.

**The cashier for sales documents**  
This code list is used to link number series with sales cash desk in different currencies. The number serie should have set the default numbering, and filled with the appropriate group documentsto make up for the sales documents and cash cash sales credit memos have given preset some values (see default values documents). At the same time the number serie must have a defined context and relationships.

**The codes from the computer**  
This code list is used to link number series for sales cash orders and sales cash credit with a specific computerEMthat is represented by the name of the computer. It allows the user to establish the sales receipt in a defined number serie based on his computer and do not need to select a number serie manually.

**The rights to the data, The permission settings on the data**  
The relevanthis user or user group, which will be responsible for the the cashier, you need to assign the rights to datathat are defined in the permission settings on the data:
-	No. – new items
-	Bank account/cashier-reading
-	Bank account/checkout-billing
-	The journal batch-posting of an item
-	Location – the posting of an item

**The default value of the documents**  
This functionality allows for sales documents, represented by the number serie or group documents predefine some value, so the user is not required each time you create a sales receipt to issue manually.
Based on the number series are usually allows you to predefine the document header and the location dimension, based on the Group documents then the default customer posting date (workdate), document date (workdate), VAT date (workdate), the default payment terms code, the default code for the shipment method, default currency code, the default price level code, etc.
These values are set when you create a sales receipt header, where the user can change if necessary.

## USAGE
The sale of spa services is done through **the Till document**. The user establishes a new till document. If a number series set up by the computer, the default value of the documents and register for sales documents, then for a new till document automatically assigns a number from the number series, the cash register on the basis of the customer's default currency, default and the location, dimensions, dates.
Spa Service, a user selects with the function "copy of the standard sales lines" in the lines of cash voucher. In the standard sales lines form the user can select one or more predefined rows. The selected rows are copied to the cash voucher, where the user or changes the quantity or selects a particular service in the field "code", if the Sale has been prestaged only "type of spa services", without a specific "Sales".
Further work with the till document is enabled by default, you can post the document creates cash entry in the g/l entries, customer ledger entries, detailed customer ledger entries, VAT entries, bank account ledger entries, etc. Depending on the composition of cash voucher. 



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)