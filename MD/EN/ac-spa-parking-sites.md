---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Parking Sites

Registration enables you to register in the system parking parking capacity and to place persons who arrived by car and stay print them a parking ticket. Registration is over Small items of the client's account.

## SETUP
**Spa Service**  
-	Service parking
	- 	This field is used to activate the instruments for monitoring capacity parking spaces
	- 	For additional services, which will cover parking and will be entering in the register of parking spaces is necessary to place a check mark in this field
	- 	If the field is not displayed, it is necessary to display it

**Parking**  
This is a spin box, where you define the individual car park and determine how to control their capaci-ty. This is an array of type checks, which can take the values:
-	No
	- 	no check for this type is not
-	The total capacity of the
	- 	in this type of checks are checks only the total capacity, i.e., that no guidance here, only the guards not to exceed the total capacity of the parking lot. When recording does not need to fill out the number of the parking spaces. 
-	Individual locations
	- 	in this type of control is checked as the total capacity, and the capacity of a specific place (standing). When you register you must fill out the number of the parking spa-ces. 
If the Check box is selected, the LICENSE PLATE of the vehicle when the additional services of type service parking is checked the LICENSE PLATE of the vehicle in the register fill.

**Blocking the parking lot**  
Across the table, parking is possible to lock the relevant parking space or across the parking lot to the selected period in case of repairs, parking of vehicles other than clients, etc.

## USAGE
Records of parking spaces is done in the form of manual entries of the service, which is accessible from the tabs stay on the client using the button "Additional services-manual entry"in the Ribbon. Parking is related to a column: 
-	Service parking
-	Parking code
-	Number of parking spaces
-	The number of vehicles
-	The LICENSE PLATE of the vehicle 
Selecting service parking automatically sets the value 1 in the number of vehicles, vehicle LICENSE PLATE NUMBER, the make up of a person's stay. Both values can be changed. 
By specifying the Počátečního data and The end date is automatically filled in the value in the quanti-ty field. The amount of services is automatically updated when you change the period of services and number of vehicles.
If the parking lot is set to check capacity, when it is exceeded, the system will produce the error message: "for the selected car park/parking is not in the required time spare capacity." This is only a warning message means that the user may consciously exceed. Then, when the entered the record of rebounds records that exceed the capacity, turn red.
If the start and end date services in a different month, you need to run the function Divide entry by month. It is important, therefore, that on the client account you cannot post an item from different months. Function splits the record into so many items, how many months is hitting. 
In order to allocate the item, you need to make it start and end date with quantity.

To register it is possible to enter a minusovou within the meaning of item cancellations. When you check the parking capacity is then this entry is deducted. Therefore, you must create a reversal in this register, not in the client account entries, in order to release occupied parking capacity.  



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)