---
title: "AC Promis - Transport"
author: Autocont
ms.custom: na
ms.date: 07/18/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: dynamics-nav-2018
ms.translationtype: Human Translation
ms.sourcegitcommit: 
ms.openlocfilehash: 
ms.contentlocale: en
ms.lasthandoff: 

---


# <a name="ac-pm-transportation"></a>Transport

## PROCESS DESCRIPTION
The process starts with the delivery of an order for the transport of the goods or manual establishment according to the operative needs of the owner or, respectively, dispatcher.

The person responsible for the completion of the shipment order shall check or modify the order of loading and unloading and with the possibility of correcting the planned times of the individual points of carriage and assign the carrier to carry out the shipment. In the case of the actual realization of the transport, they will allocate the necessary resources. Before the completion of the shipping order preparation process, M&G tools create section itineraries between each point of transport, calculate the times and distances required for implementation according to the plan. In the case of shipments made with own resources, the dispatcher can modify the route in map data. The dispatched shipping order will be sent to the communication device of the assigned vehicle.

In the case of a lack of own resources, the order for shipment may be offered to the subcontractor. The demand for the sub-carrier is managed by the responsible person (the dispatcher), who, according to the agreed conditions, subcontracts the price for the realization, the vehicle number, car or contact with the driver. Submissions for the transport of the subcontractor are sent in the form of a press kit containing information on the points of loading and landing with the times in which the various places are to be served, the contract price for the transport operation and eventually. the necessary shipping and delivery terms.

During the implementation of the transport, the dispatcher monitors the state of implementation of the individual loading / unloading, checks the electronic collection of data from his / her own vehicles and communicates with the driver if necessary and provides the backoffice for implementation. The driver enrolled in the vehicle shall enter data on the activities performed using the communication device. These data are transmitted online for processing into software that serves dispatchers to track vehicles (Transics or Webdispečink). The NAV downloads and processes these data at regular intervals. On the basis of these, it evaluates the state of implementation of individual transport points and therefore the state of realization of the individual commodities that are connected to these points of transport. In the case of a subcontractor's implementation, the progress data is entered manually by the dispatcher (eg actual arrival time on loading).

Carrying out and documenting accompanying documents, which are proof of the loading or unloading (Shipment, CMR, etc.), are part of the transport operation. Accompanying documents serve as a basis for billing, so the driver carrying out the final stage of the shipment is obliged to return all the confirmed accompanying documents back to the registration in the NAV.

After completing the shipment, the person responsible carries out the completion of the data and the control of the accompanying documents. If the documents are complete, the billing process may be initiated.

### ALLOCATION OF TRANSPORT SOURCES
Transmission resources are assigned with respect to the supplier who was designated for the transport operation. In the case of implementation with own resources, the timing of the resource is checked when assigned to transport. It includes checking that the vehicle, the car or driver is not assigned to another carriage at any given time or does not have a planned absence at a given time (vacation, training, doctor...).

In the framework of the transport, the dispatcher has the possibility to check the fulfillment of the requirements, restrictions and properties of consignments, distribution points used for transport, country of distribution points of distribution against the properties and restrictions arising from the assigned vehicles, wagons and drivers on transport.
At the same time, the dispatcher is alerted to the upcoming technical inspection of the vehicle  / truck the vehicle specified on the respective source card.

In case of implementation with external sources, the real availability is not controlled when the source is assigned to the transport, but only the availability in the planned IS transports. It is not the goal of keeping records of the entire time schedule of external resources. The subcontractor is responsible for providing a free external resource. When using external carriers, it is possible to inspect their insurance records.

#### Availability of own fleet and drivers
The responsible person (dispatcher / dispatcher) has several tools available to help him track not only the actual availability of his / her own vehicles / cost. wagons and drivers, but also get an overview of where and when the last scheduled carriage of individual vehicles ends. This enables operators to respond operationally to a further potential contract, minimizing the cost of moving vehicles between shipments. This is especially the Vehicle Timeline.

This form allows:
- Show booked time of individual sources (vehicles, drivers, trucks).
- View color-differentiated reservations by type Absence vs. Transportation.
- Show name of reservation - text only.
- Open from a specific reservation a link to the appropriate ticket or absence.
- Switch the timeline display to Minutes / Hours / Days / Weeks, with the same number of slots (about 70) always displayed.

An overview of your own free vehicles with the latest scheduled shipment in the required country / city to the current day.

### CALCULATION AND ADJUSTMENT OF ROUTES
Each shipment includes at least two geographic locations between which a route is needed. This is basically a definition of the order of each line of transport, to facilitate the system includes a link to an external system.

You can edit your route itineraries by adding your waypoints and update your mileage and time calculations as you make adjustments. Thanks to this integration it is possible to display an itinerary in map data.

The system uses route tracking calculations to track existing itineraries that can be created manually without current transport needs or generated on the basis of scheduled shipments. Itinerary records allow you to take into account the experience of dispatchers, drivers and other features that can not be calculated accurately. The information entered on a particular itinerary is used for its further use on shipments. Alternative routes for a given section (itinerary) may also be part of the record, and one of them is defined as the basis for transport planning. The dispatcher may choose another route variant operatively on the shipment.

#### Integration with Map & Guide
To simplify the route calculation between each transport point, the system is integrated with Map & Guide maps. Each route profile may include a custom setting of conditions for optimal route calculations taking into account, for example, height, width, length, total weight and axle load limitations, prohibitions and limitations of passes, and more.

This is the calculation of net mileage and time for transport in the already planned order of seats that need to be serviced by the vehicle with the required profile. The planned route calculation does not take into account the predicted driving and resting times, the remaining driving time and the remaining shift times of the driver or crew.

After determining the profile of the transport route (eg trailer with trailer, van, passenger car, truck with dangerous cargo ...), the map server is asked to calculate the individual sections of the route on which the shipment is divided. For sections of own-source transport, the NAV is based on an initial and destination route in detail of the points of transit points, together with information on tolls paid and unpaid by country and the distribution of charges within the itinerary. For transports performed by external carriers, only the calculation of the kilometers and times required for the implementation of the section is recorded and recorded in the transport.

The ramp of the assigned vehicle is also included in the calculation of the planned route, which is updated based on the end point of its previous shipment.

### CALCULATED COSTS AND TRANSPORT PROFIT
The estimated mileage and the time needed to realize the shipment are the basis for calculating the calculated transport costs. For the realization of transfers by own resources, the possibility of parameterization of the individual rate per kilometer and per hour of the vehicle in relation to the profile of the route calculation (delivery, tractor with semi-trailer ...) and transit of the given transport are used to determine the calculated costs.
Freight costs incurred by external carriers can be quantified using a valid pricelist. For individual external carriers, pricing can be set according to the planned distance, the unit price for the commodity, or a flat rate for the transport.

Internal calculated costs and contract costs of transport performed by an external carrier are recorded in the form of billing lines. This form of cost accounting makes it possible to dissolve their amount on the commodities of the individual packages included in the shipment in the kilometer share algorithm of each commodity. The result is an immediate quantification of the profit / loss of the transport by comparing the planned costs set for the transport and the sales prices of the consignments made by the shipment. Dissolving costs directly on individual commodity shipments also allows you to quantify the profit / loss of individual consignments or sub-items.

### TRANSPORT MANAGEMENT AND IMPLEMENTATION
Confirmation of transport, containing all the necessary information for implementation, generates the items of checks that are required for the monitoring of the actions during the transport realization. The rules for creating control items in relation to individual types of shipping lines can be defined according to the company's needs. By default, only the confirmation of the start is required for the raid, while loading or unloading requires confirmation of arrival and departure from the place in two separate events.

#### Integration with Transics, WebDispečink
If the company uses in-car units from Transics or Webdispečink in its cars, the Schedule of Shipment (items for individual shipping lines) is sent by the dispatcher to the vehicles directly from the order of the transportation in the NAV. The driver receives information on the transport request and acknowledges his receipt to the on-board unit. The actual commencement of the shipment is effected either by confirming the first point of transport by the driver (usually the commencement of the raid), or automatically based on the termination of the last point of the previous completed transport.

The driver is prompted to confirm the action being taken in the vehicle communication device at the stop, eg arriving at the loading or unloading point. After resuming the vehicle and taking a defined distance from the place where the arrival action has been confirmed to the desired location, a confirmation of departure may be made automatically, or the driver can confirm manually in the vehicle communication device by the action of departure from that location.

The on-board monitoring unit continuously records the travel and transport data and sends it to the central system (Transics, Webdispečink ..). From there, the data are downloaded at regular intervals to the NAV and on the basis of them, the state of implementation of the individual points of transport and therefore the realization of individual commodity shipments is updated in the IS.

#### Transport Tracking Desk
To monitor the state of implementation of individual points of transport, the so-called Transport Tracking Service is used in the NAV. The dispatcher can see where the vehicle is located or whether it is on the way between two points and show the current position of the vehicle on the map.
In the Pulley, it is also possible to manually add missing data if the driver in the vehicle does not perform the required action confirmation or if it is an error in communication with the monitoring device. The dispatcher has an online overview of the realization and event event. data editing according to the actual realization.
When performing a subcontractor transport when data from external vehicle monitoring equipment is unavailable, the monitoring desk is used to manually add data on the implementation of individual transport points.

The dispatcher has the ability to filter records in the Watching Path so that it can track transports, for example, assigned to it, or transport of a certain type, in a time sequence.

#### Track Plan Completion
In the checkpoints of the individual points of transport, the completion of the actual time of the given check is carried out confirmation of realization and evaluation of the fulfillment of the real time time reserve against the scheduled according to the set rules. At the same time, the time sequence of transport points is checked, such as that landing can not be preceded by loading, or departure from the place of transport can not be preceded by arrival at a point and other.

#### Vehicle Message Board
For on-line communication with the vehicle, a vehicle message board can also be used to allow the dispatcher to send a message to one or more vehicles at a time. The console displays both incoming and outgoing messages in communication with the vehicle. The counter is used to communicate via WebDispečink.

### EVIDENCE OF TRANSPORT DOCUMENTS AND PREPARATION OF INVOICING
Each customer order (Ship) contains a list of required shipping documents. Each Consignment in theory may contain a different type of accompanying document.
After the actual realization, the collection and registration of these documents is carried out in connection with the original orders of the customer. The physical collection of documents is carried out according to the possibilities of drivers and companies.
Another responsible employee, on the basis of the identification of the customer's order (shipment) from the submitted document, makes his registration in the IS.

Once the required documents are attached and the consignment price is checked, the document may be billed. When checking pricing before billing, you need to take into account whether the billing is based on the quantity ordered, the actual execution, or whether the unrealized quantity is not to be billed because the reason for not delivering it is not shipping.

### EVALUATION OF TRANSPORTATION PROCESS
From software that records vehicle movement and driver actions during transportation, data is continuously downloaded to NAV and recorded on vehicle items and activity items.

On the basis of control data, the dispatcher can perform a manual evaluation of the progress of the individual points of transport, but also carry out a transport evaluation as a whole. The dispatcher during this evaluation can verify the correctness of entering the data by the driver directly in the activities recorded for the given shipment.

### DRIVER ACTIVITY DRIVER
Data on driver or crew activities is continuously assembled from the monitoring sw and is fed into the Driver Activity Log overview. The log may be supplemented manually if the data from the monitoring device is incomplete or if it is a vehicle without a monitoring device.

Journal entries can serve to further evaluate the driver's work, such as the number of loads or landings made, the time spent by each activity during the implementation, work on weekends or holidays, etc.
Logbook entries also serve as a basis for calculating drivers' work paths by country performance and eligibility for subsistence.

## <a name="see-also"></a>See Also 
[AC ProMIS](ac-pm-promis.md)