---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Contracts

Contracts are recorded in the system on the The contract tab. The individual cards are numbered automatically based on the number series as defined in the General settings. Paper contract number can be entered in the Formal contract number.
Important fields on the header Card contract:
-	The formal contract number = number on contract
-	Name = name of the contract
-	Contact type = the resource for which the contract is intended. The possible choices are:
	- 	Vendor
	- 	Customer
	- 	Client
	- 	Doctor
	- 	Employee
-	Contact No. = number of resources by type. The name of a contact from the contact table is added according to the setting, create a name
-	The code of the main subject = main subject of the contract
-	Code of responsible org = organization section of the Department, which is responsible for the contract.
-	The code of the location of the original Treaty = store
-	Signature date = date of the signing of the contract
-	Valid from date, to date = force of the Treaty
-	The formula data note – here you can define a date formula, which has a system to notify the fact to the set, for example. the contract expiration date. 
	- 	The functionality of the warning module Upozorňovátko, which It is used for example. to hlídání dates on documents (delivery date, maturity, the expiration date, date of notification). It is possible to inform employees about the timeliness of the term mail (checks, performance, meet, ...). For each table in the system, which is to be monitored by the so-called Upozorňovátkem, is set. Templates tab of the event. On this tab are specified for more restrictive conditions, IE. Upozorňovátko may not work with all the records from the table, but only with the selected subset.
	- 	To each template are further defined phase of the event, i.e.. the States that are in a specific item may Upozorňovátku events. The stages are listed and detailed rules for their use that reference for example. on the formation of the record or the exact date field.
	- 	Create and update your own mail Items is solved by running the report notification (either manually or by the Scheduler).

In the articles of the Treaty It is possible to register other articles of the Treaty, allowing its inclusion in multiple groups according to the subjects addressed. 

If the contract belongs to the source additions to your number, you should register as an additional contract and with this the main contract is to combine the functionality of the Connection by using the related contracts function connect the related agreement in the Related contract.  



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)