---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Business Register 

The functionality of the business register allows you to associate contacts with the same IDENTIFICATION NUMBER. Uses a connection to the ARES, the control of VAT and the unreliability of the payer's control that are part of the functionality of the Localisation ENG. 
Commercial register has separate registers, that it is conducted on the commercial register and also your settings. Already at the level of the commercial register can be used to perform a number of checks associated with IR and create contacts, customers, and suppliers. 
Business Register setup
-	The default template for customer/vendor
-	Numbering of contacts, customers, suppliers
-	Reference to the register of ARES
-	Bank account synchronization settings
-	Customer and vendor synchronization settings when deleting contacts

Classification of Business Register
-	To view the descriptions of the classification it is necessary to fill up the list of codes, classification OR, otherwise, the update of ARES are being fulfilled only codes (description is not included in the xml file).

Business register card

-	ARES Update
	- 	is made through the Authentication Protocol ID. It can be run by using the update button ARES in the Ribbon or through the AssistButton next to the field IDENTIFICATION NUMBER
	- 	If the system finds for the ID record in the database registration. entities creates a log entry with a status of valid, and as far as the first authentication, it opens the data update form at the same time, otherwise, you can open the form by clicking Update tab. When you open the form, it will automatically compare the data from the card of the commercial register compared to the recorded data from the registry database. In the case that the data are identical, the update form does not open and the message appears to the user that the data are the same, and there is nothing to update. Otherwise, opens the update form with the information of Ares do not match with the automatic check for updates. By default, the update automatically selects if the record in the spring provides information that is not in the registry. The user can decide what you want from the registry update with a check mark in the appropriate box. The update is carried out with the OK button.
	- 	On invalid entries, automatically sets the ground for invalidity in the validation result
	- 	View ARES on the Web is made possible via the button in the log ID verification 
	- 	Each time the function to verify the COMPANY ID is setting up a new entry in the log ID verification

-	Check VAT REGISTRATION NUMBER
	- 	Is made through the check button in the Ribbon or TAX EXEMPT NUMBER through the AssistButton next to the field VAT REGISTRATION NUMBER that starts the authentication protocol. The log lists each authentication States and new authentication is by using a function to validate the VAT number.

-	Check the unreliability of the VAT payer
	- 	The button Control is via the unreliability of the VAT payer in the Ribbon. Function checks to see how the Bill and its registered bank accounts. After their checks the user shall notify the number of items that the user can open the unreliability of the Status button from the Ribbon.
	- 	The result of the date of the inspection and the unreliability of the function at the same time writes into the appropriate fields on the Details tab of the commercial register
-	Create a contact – this function creates a new contact with the data from the OR, but without an address
-	Create a contact with address-this feature creates a new contact with information from OR
-	Create customer – this function creates a new customer through the customer template
-	Create vendor – this function creates a new vendor through supplier template 



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)