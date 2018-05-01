---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Stay Campaign

Another marketing tool of the Spa solutions are the residence of the action.
Residential action
Residential action can be set up in the Residence of the action. According to the specified conditions can one stay fit for several events at the same time, the system then selects the most favourable to the client.

Tourist action is based on a defined number of occupant days free (e.g. 7 for 5, 14, 12, etc.), which are applicable in the event that the achieved number of services for the application of the action is > = the basis for calculation. The application connects to the service with the largest number of days.
The days of free are in the client account as a new item with a negative quantity and number of tou-rist events.

The importance of the fields:
-	Client type code field, the code type of stay, number of the payer, the spa house Code, the code of the dependence and the date of commencement – serves as a condition for the se-lection of the action to stay. 
-	Arrival day is related to the starting date of the stay.
-	Start and end date – the validity of the action surrounds
-	How to check the
	- 	Service code – check the necessary number of services for the application of the actions is carried out through the service codes
	- 	Service categories-check the necessary number of services for the application of the actions is carried out through the service categories that can be defined for specific services in the category code (in the Spa Service). For the calculations are then added together from the same category.
-	The type of items for control — determines what items will check their quantity in relation to the basis for calculation. The action will be applied only in the case where the control quantity is > = the basis for calculation.  
	- 	All – for the application of the action will take into account the Control quantity of all services included in the control of actions, of which shall be selected a minimum quantity and it checks the value of the basis of calculation. If greater or equal to, the action will apply.
	- 	Curative stay-for the application of the action will take into account only the control number of services treatment included in the control of actions, of which shall be selected a minimum quantity and this is checks the value of the basis of calculation. In the case that will be the same or greater, the action will apply. And even if that control the amount of accommodation services or meals will be smaller.
	- 	Accommodation -for the application of the action will take into account only the control a multitude of services to the property included in the control of actions, of which shall be selected a minimum quantity and it checks the value of the basis of calculation. In the case that will be the same or greater, the action will apply.
	- 	Catering -for the application of the action will take into account only the control number of services catering listed in control of events, of which shall be selected a minimum quantity and it checks the value of the basis of calculation. In the case that will be the same or greater, the action will apply.
-	The basis for calculation-defines the amount of which must be achieved in audited services to application of action
-	The posted quantity – this field indicates the number of billable days. The difference charged to days and then form the basis for calculating the days free of charge.
-	Use the property, eating, cleaning – using these fields, you can define what types of services the action will be invoked in the case of the fulfilment of defined conditions.

**Spa Service**   
With Stay campaigns relate to 3 fields:
-	Code of a category – allows you to check the number of services for the application of the action on the basis of some common properties and merge several service codes
-	Include in the control events-allows you to include service to the control mechanism for the determination of whether to stay with the Services complies with the conditions defined by the action
-	Include in the application of the discount events — allows you to apply the discount to the service according to defined conditions of tourist events

**Setting Spa General Ledger**  
With Stay campaigns relate to 3 fields:
-	Process action on the last day of residence-if the field is selected, the action is calculated to the end of your stay when you post
-	Include the supplementary payer to events-if the field is selected, the action will be counted for the supplementary payer (by default, the events included the main payer)
-	Include the client events-if the field is selected, the action will be counted and for items paid for by the client

**Setting the type of stay**   
With Stay campaigns relate to 2 fields:
-	Perm residence events – check in the field enable events for a given combination of client and type of stay
-	Available to enable the events — a check mark in this field allows you to set permission on subsistence actions on particular tab of the client's stay, which is based on the combination of the type of client and residence 



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)