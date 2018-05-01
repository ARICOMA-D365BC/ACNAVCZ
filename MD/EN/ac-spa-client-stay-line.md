---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Client Stay Line 

In various States of residence of the client, you can add new rows staywhich can then be individually manipulated by using features in the Ribbon for lines:
-	Design of the standard lines
-	Make a reservation of the selected rows
-	Cancel the checkout of the selected rows
-	Cancel check-in of the selected rows

System to reflect the diverse client requests for accommodation, using a variety of fields from the line:
-	Start date – represents the starting date of the booking or the cast of accommodation
-	End date-end date of booking or represents occupancy accommodation
-	Start date of the posted document. accommodation – represents the starting date of the accommodation, which is charged to the client
-	End date posted. accommodation – represents the ending date of the accommodation, which is charged to the client
-	Early arrival – this field is important for rows of type property. Can have the values:
	- 	No-default value. 
	- 	For an additional fee-for the request property is required early arrival, which will be charged to the payer in the value of the premium
	- 	At no extra cost – for the request property is required early arrival, will be charged
-	Occupy the capacity for early check-in-check performs a cast of accommodation for the night prior to arrival and at the same time sets the values into the fields: the initial billing date property and accommodation booked from the date
-	Accommodation reserved from the data, the value in this field specifies the occupancy of accommodation capacities
-	Expected time of arrival – here, the user can specify the expected time of arrival of the client. Is an optional field, its value appears in the cast of accommodation capacities.
-	Late check out – this field is important for rows of type property. Can have the values:
	- 	No-default value. 
	- 	For an additional fee-for that request late check-out is required, which will be charged to the payer in the value of the premium
	- 	At no extra cost – for that request late check-out is required, which will not be charged
-	Occupy the capacity for late check-out-check performs a cast of accommodation for the next night after the end date, and at the same time sets the values in fields: end date of posting, lodgings and accommodation booked into the data
-	Accommodation booked into the data, the value in this field specifies the occupancy of accommodation capacities
-	The expected departure time – here the user can specify the expected time of departure of the client. Is an optional field, its value appears in the cast of accommodation capacities.
-	The type of relationship data property – new this field specifies the relationship between the charged data (starting, Ending posting date of accommodation) and the reserved capacities (accommodation reserved from, to date). Can have the values:
	- 	Identical – the posted data is identical with the reserved capacities
	- 	The offset of the starting date — allows you to offset the "starting date posted. "back off" of the accommodation capacity of the checked-out from "about the value in the" to modify the number of the posted days accommodation "
	- 	The offset of the end date — allows you to offset "the end date posted. "ahead of the" Accommodation capacity reserved to "value in the" to modify the number of the posted days accommodation "
	- 	All data-allows you to offset the offset of the "starting date posted. "back off" of the accommodation capacity of the checked-out from "and at the same time offset" the end date posted. "ahead of the" Accommodation capacity reserved to "value in the" to modify the number of the posted days accommodation "
	- 	Manual input – allows you to manually specify the starting or ending date "accounts. accommodation ". However, the dates must be specified outside of the original interval.
-	Modifying the number of days of accommodation – always charged to enter a positive value. Rewind or forward specifies the value in the field "type of relationship data property". 



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)