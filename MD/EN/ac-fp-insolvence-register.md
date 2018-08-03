--- 
Title: "insolvency register"
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

# ## <a name = "ac-fp-insolvency-register" > </a> insolvency register
Add-on insolvency register are used to register the records from the https://isir.justice.cz of the insolvency proceedings of companies. It is an instrument for further action, with the contacts that are in insolvency proceedings, for example. When you enter sales documents, posting them (delivery, billing). Provides to the people of the company the current information on the new records in the insolvency register.

# # Set

### Spooler Settings
 For importing records from a Web portal of the insolvency register is necessary to set:
* Agent-agent to receive records from IR to the NAV database
* Task spooler
The setting is made in the application settings management > > Spooler > Agents.
Communication with the public is through IR databases public Web services at:
https://isir.justice.cz:8443/isir_ws/services/IsirPub001
This address is specified as a parameter to the agent for the receipt of communications IR record.
Manage application settings > > Spooler spooler > Jobs

### Set the insolvency register
In the insolvency register Settings are available the following items:
** The number of the last action **-last used ID of table Action insolvency register.
* Update the status control ins. ** register-defines whether the workagent will automatically complement the table (dial) "insolvency register control status" when receiving IR events.
** Update type of event an insolvent register-defines whether the workagent will automatically complement the table (dial) "insolvency register event type" when receiving IR events.

# Work with insolvency index

### General
The functionality of the insolvency register is available in the main menu, the sales and marketing.
Evidence of ongoing IR is available on your system:
* The things insolvency register
* The contact card
* The vendor card
* The customer card
* The company settings tab

### Card case insolvency register
Card case insolvency register provides the user with an overview of all current events of one of the insolvency proceedings. The data are also included information about the names of the borrowers, the caretakers, the control state, dates and times of publication, etc. 
* Tab * General * * includes manually editable item ** "State of things" [option = open, closed]. The responsible person in the company, therefore, will be able to after own discretion to decide whether some of the insolvency proceedings shall conclude by setting the field Status = closed Case.
In addition, the card contains a field ** Reviewed ** where the user manually selects, that carried out the inspection. 
Bookmark * administrator * provides information about IR Manager (such as name, address, company registration number, VAT NUMBER, social security number).
The lines of the card case insolvency register displays data from a table 4003802 Event of insolvency register. The values in the rows are grouped according to the values of a section (A, B, C, D, P) field in the Event of insolvency register. A number that indicates the order in line means a specific tab.
On the things you can ** IR button Thing * * display the following data:
* Overview Of F5 
* ** **-Contains information on persons involved in the management of a specific case of insolvency proceedings. For persons who can view their address. 
We distinguish 2 types of roles in the proceedings: 
* Administrator
The debtor
** Button * Line * contains * a * "view document" attached to a particular line. Its location is specified in the ID column of the document. Documents are not stored in the system. In the lines is only a link to a file in a public database. 

### Register of insolvency proceedings for a contact
The contact card is on the button Contact > insolvency register complemented by the ability to view the registration of insolvency proceedings relating to the company or person. The identification is based on the IDENTIFICATION NUMBER or social security number information. 
Contact card also includes the indicator of the number of records in the table Thing. The indicator is located next to the icon of the notes (pencil) and allows you to view the records of IR for the contact. 
The indicator shows the 3 possible States:
* No record (not displayed)
* There are closed records in IR ("(0)")
* There are active (to be finalised) records in the IR (e.g. appears. "(2)" — a number representing the number of open records IR)

### Register of insolvency proceedings for customer card
The customer card is on the button Customer > insolvency register complemented by the ability to view the registration of insolvency proceedings. The identification is based on the IDENTIFICATION NUMBER or social security number information. 
The card also contains the same number of records in the table indicator Thing such as IR on the contact card.

### Register of insolvency proceedings in the vendor card
The Vendor tab is on the button Customer > insolvency register complemented by the ability to view the registration of insolvency proceedings. The identification is based on the IDENTIFICATION NUMBER or social security number information. 
The card also contains the same number of records in the table indicator Thing such as IR on the contact card.

### Register of insolvency for company information
The company information tab is on the button Company > insolvency register complemented by the ability to view the registration of insolvency proceedings relating to the own company. The identification is based on data of the IDN.
The card also contains the same number of records in the table indicator Thing such as IR on the contact card.

### Test the shut down option on the insolvency 
For performance reasons, it is possible to control the insolvency register for selected contacts (e.g. foreign) off. For these purposes, you can use a boolean "Disable test on insolvency".
Boolean is placed on the foreign trade tab on the contact card, the customer card, a vendor card.
The value of the booleanu shall be validated from the contact card for the customer card and/or to the vendor card, and vice versa. 
In the process of checking the insolvency register for contact cards not NAV to browse those cards that have a boolean "Disable test on insolvency"--YES. In that case, ignoring things card occurs in insolvency proceedings, it is not an indicator of the number of insolvency proceedings, posting takes place normally. 

# Work with IR in sales documents

### Sales &amp; Receivables Setup
In the sales &amp; Receivables Setup it is possible to define the behavior of the system with respect to the records in the insolvency register.
* "Check box when the insolvency" ** [option = "empty" Warning, Blocking], together with the "block post insolvency" determines the behavior of the system as follows:
** the "empty" ** – the check is turned off 
** Please note **-when you post form is shown with a warning that "a customer's record in the IR, asking whether the user wants to continue yes/no". Form displays the number of open/closed records.
** Block ** – it is not possible to post delivery, invoice, or both, according to "field settings to block posting of insolvency *. 
The field "block the posting of insolvency" ** [option = "empty", add to invoice all] – associated with the selected option in the "insolvency" Review
** the "empty" ** – blocking is turned off 
** Add ** – the document is not possible to post the delivery if the customer has an open record in IR. 
* Invoice * – the document is not possible to post the invoice if the customer has an open record in IR. 
** All ** – on the sales document, it is not possible to post the delivery invoice if the customer has an open record in IR. 

### Warning on sales documents
When you insert a customer on a sales document (an order, invoice, bid) will be in the event that the customer has a record in the insolvency register, the form is displayed with information about the number of open and closed records in IR. 
A warning message is displayed for customers with status IR open as well as closed. 

### Posting sales documents
According to the sales &amp; Receivables Setup, the system will, in the case of the existence of open records the customer's insolvency register alert or completely block the posting of delivery and billing.
It is possible to block the document release through the box "enable posting of insolvency". The field is located in the Prodejní objednávka form on the Shipping tab and in the form of a sales invoice on the General tab.
The field "Enable posting of insolvency" may only place a user in user controls "field set to enable the insolvency exclusion". 

## Warning Reports on insolvency proceedings

### General
In connection with the IR are available 2 basic reports for notifying users of the existence of the IR for partners in the database at the same time also for the NAV and case submission IR on their own company.
* Check the insolvency register 
* An overview of sales documents in insolvency

## # Set SharePlanu
Both reports can be accessed through the Task Scheduler on the application server and automatically send the responsible persons by email. To do this, it is necessary to create a Tasks tab, SharePlanu, intervals in the planning tab and set the parameters of the report. 
On the button ** Task ** > Action can be defined for the sending of report data by email. 

### Report checking the insolvency register
Report automatically draws attention to the input of the business partner (contact/customer/vendor) into insolvency proceedings, or to the submission of the application for insolvency proceedings against your company
The data source is a table Thing insolvency register. In the report it is possible to set these parameters:
* Reverse-field is used to enter time/date interval from when the user requests the report start backwards. (it is possible to enter a date, or a value in the form of a flag, e.g. 3D 5 h = 3 days 5 hours ago. For the needs of more detailed monitoring of the insolvency proceedings, too, M = minutes, S = seconds)
* Do not print their own company-report will not contain the record of the IR that started at his own company.
* Do not print contact-report will not contain the contact lines
* Do not print the customer report will not contain the customer's lines.
* Do not print the vendor-report will not contain the lines for the vendor.

### Report an overview of sales documents in insolvency
Report automatically draws attention to the existence of sales documents on the system, in which a customer record in the insolvency register and:
* Unposted orders
Open customer ledger entries of all types (invoice, payment, credit memo, finance charge memo, reminder)
* Reminders
* Finance charges
The data source is a table of the sales header and customer ledger entry. In the report it is possible to set these parameters:
* the filter according to the data from the customer card
* According to data from the header filter sales documents
* filter according to data from customer ledger entries 
* Including concluded proceedings – if checked, displays and documents for customers who have closed records in IR.

## <a name = "see-also" > </a>See Also   

[AC Financial Pack] (ac-fp-financial-pack.md)
