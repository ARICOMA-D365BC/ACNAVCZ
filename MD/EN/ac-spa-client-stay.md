---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Client Stay 

Stays are registered on the client stay tab that represents a key register in the system. The information that is important for keeping records residence, are divided into several tabs according to content. The key information is displayed even when closed tab.
Stay tab passes through several States, depending on the course of the client's stay:
-	Request
	- 	This is the default state. Is automatically assigned when you enter a new stay. 
	- 	In this state it is possible to get the status of your stay:
		- 	"Reservations"-with the function "Cancel booking"
		- 	"The arrival"-by using the function "cancel check-in"
		- 	"Cancel" – with the function "Come back Cancel stay“
	- 	 In this State can be changed for individual stays most of the data, if it allows the restrictions defined in the settings. A stay is the only recorded, are not reserved any accommodation.
-	Booking
	-	Reservation status indicates that the client has in the spa house booked accommodation. By changing the the starting or the end of the data in the row is automatically changing the booking of the accommodation capacity.
	-	In this state it is possible to get out of the State of residence:
		- 	"The request" - with the function "reservation"
		- 	"The arrival" - with the function "Return check-in to checkout"
	- 	Booking may refer to:
		- 	Fixed – reserves directly to a particular room listed in the prompt type property
		- 	Free – reserves the accommodation categories listed in the type line. The system internally of stay shall be allocated a room in that category, however, may change if the room will require another client. The system automatically moves the free reservation to another room in the category.
-	The arrival 
	- 	This status allows all operations associated with the physical arrival of the client
	- 	Resident, the client receives the keys to the room, he will occupy accommodation capacity, may to the doctor and on the breakdown of procedures. 
	- 	In this state it is possible to stay out of the State:
		- 	"Request"-using the "Arrival"
		- 	"Reservations"-using the "Arrival"
		- 	"Income" – by using the function "cancel income"
		- 	"Convert"-with the function "Cancel transfer"
-	Income
	- 	This State is used to perform administrative tasks that are associated with income, such as. check the personal data of the client, that correspond to the data entered in the system, and any updates, fill out a visa, foreign police. 
	- 	In this state it is possible to stay out of the State:
		- 	"The arrival" – by using the function "income"
		- 	 "Convert"-with the function "Cancel transfer"
		- 	"Departure"-by using the function "cancel check-out"
-	Interrupt
	- 	The status of the interruption of the client's stay on the card indicates that the stay of the client is interrupted for some reason. Stay in this state gets by using the wizard, in which you determine which service the interrupt, for how long and for what reason.
-	Convert
	- 	This status indicates that the client was during your stay duration converted to a different type of residence by using the Wizard "guide the transfer of their stay". 
	- 	In this state it is possible to stay out of the State:
		- 	"The arrival" – with the function "Transfer to a new type"
		- 	"Income" – with the function "Transfer to a new type"
-	Departure
	- 	This status enables the operations associated with the physical departure of the client. 
	- 	Performs the checks associated with the departure of the payer, if they are set up.
	- 	In this State, the client is not eligible for the service. Phone account expires, you cannot control the timing of the procedure cannot be pasted items on the client's account originating from other sources (e.g., from the restaurant, the breakdown of procedures).
	- 	In this state it is possible to stay out of the State:
		- 	"Income" – with the function "check-out"
		- 	"The end" – by using the function "cancel end"
-	End
	- 	This State is used for administrative operations that are associated with the end of the stay, such as. edit items on the client account, the payer is not the client.
	- 	In this state it is possible to stay out of the State:
		- 	"Departure"-using "End"
-	Cancel
	- 	In the State of residence may be transferred only from a State of „Request"(using" Cancel! ") in the event that the client did not arrive. Only in this State, it is possible to add to the client account cancellation fees.
Activities and functions that you can perform with the stay, are accessible in the Ribbon depending on the State of residence. 



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)