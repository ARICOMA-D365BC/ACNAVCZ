---
title: "AC Promis - Shipment Invoice"
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
ms.contentlocale: en-en
ms.lasthandoff: 

---


# <a name="ac-pm-shipment-invoice"></a>Shipment invoice

The business case begins with the buyer's demand for the transport. The request may arise on the basis of a long-term agreement between the customer and the supplier of the contract-based service, or also on the basis of the current need of any customer without pre-arranged contractual terms.

The customer is registered in the system as part of the Register of Customers, which records, among other things, data such as the method of receiving orders for the transport, the price list, the date and manner of implementation, the method of invoicing, etc. The customer card must be registered in the system before the actual realization receive orders.

When recording an order, you can select or acquire the data directly related to the order book. These include, for example, loading points, landing sites, but also the specification of the actual subject of the shipment. Depending on the method of communication, the data may be set automatically according to the agreed rules, but the data related to the order is searched for and based manually. The system includes support functions that allow the owner to use already recorded data to prevent duplicates in individual dials. Data from previous business events of the given customer may also be used.

Part of the order picking process (so-called Shipment) is the pricing of the service. It can either be a contract or an agreement. In order to determine the sale price, the system assists in calculating the estimated costs or by comparing costs and revenues from similar orders from the same or another customer. Pricelist variability makes it possible to define prices by type of goods transported, by volume or weight of transported goods, according to the number of goods pallets transported or the entire cargo within the shipment, all in relation to the place of loading or unloading.

Last but not least, it is the task of the agent to arrange the order for implementation according to the requested deadline and the place of transport and the possibilities of the company. It is possible to connect a shipment to an existing scheduled shipment or to create a completely new request, usually after consultation with the dispatcher. By handing over the consignment to the dispatcher, the receipt process and the ordering of the customer's order end.


## RECEIVING THE CONSIGNMENT
The order from the customer for the transport is in the system registered with the Consignment. In addition to standard requirements such as who and when commodity shipments have been ordered, the consignment also includes specific requirements related to the ordering of goods transport.

### General information about the shipment

The first step of registering a shipment is to add customer information. If the requested customer is not yet in the customer list, it will be established via the contact list. Further details can be a reference to the customer's order number, the type of vehicle you require, the identification of the person in charge of the shipment, the type of shipment, the date of the order and the type of price calculation from which the price list is based.

To create a shipment, you can use the feature to copy an existing shipment, a wizard to find a similar shipment, and a copy of the shipment, or to create a re-export.

### Loading and unloading
You can use the shipping lines to specify the loading / unloading location and the required delivery times. Each shipment must contain at least one place of loading and one place of unloading. When determining the place of loading and unloading, the holder can choose from the distribution logs already registered in the system or from the shipping line directly from the shipping line.

### Commodity shipments
The consignment must also contain at least one commodity (the goods being shipped) with a non-zero amount. Each commodity must include a link to the line of loading and the line of unloading of the consignment. Optionally, it may include additional information such as weight, volume, number of pallets, external loading or unloading code,

### Realization price
To complete the receipt of the shipment, the price is determined for the transport of the required commodities. Consignment prices are recorded through billing lines. The consignment can be valued on the basis of defined customer pricelists, manual price insertion, or based on expected cost calculations based on communication with M&G map data. The consignment also contains a function for comparison with realized shipments from historical data.

Shipment information panels provide not only a wealth of information for operational decision-making, but also operational information with the ability to quickly move documents for the delivery and billing of the shipment. Within these panels, the user can also track the commissioning of the shipment.

### Related Services
If a transport service is required to implement the shipment, but the transport company does not provide this service, the service order can be registered as part of the shipment. These are services such as repatriation, customs clearance, etc.

### Status Management
The consignment contains multilevel state management from various perspectives that capture its state of planning, implementation (in terms of shipping) and billing of the shipment. These states are independent of each other.

### Complementary functionality
The consignment contains general and accompanying text tools to record specific shipping requirements from different sources (customer / distribution point, commodity ...), eg delivery terms.

### Integration order receipt
The standard functionality of the module does not include tools for importing orders. Integration is done individually based on customer requirements and delivered structures.

## PLANNING AND OPTIMIZATION
To plan the realization of shipments without the use of planning methods, there are a number of support functions in the NAA to facilitate working on a transport plan with a wide range of user options for how to implement:
- Creating an order for shipment from a shipment in a 1:1 binding, ie one shipment makes only one customer order.

- Creating a shipping order by including multiple shipments in one shipment (N:1), so one shipment makes more orders. The shipment may include shipments of different customers, but also shipments with different points of loading and unloading required to serve the order. The list of items so included in the shipment is fully directed by the shipping dispatcher.

- Insertion of one or more shipment at one time into an existing shipment.

- Distribution of one consignment into multiple shipments (1:N), whether due to the need to distribute freight in time-conveying operations, or to realize the transport of cargo in the form of a progressive fulfillment of the delivery of the consignment.

- Division of the consignment into sub-parcels for deployment in the depot and location of individual sub-units for different shipments. This model allows for the realization of shipments in the form of a so-called collection service, or the use of Linehaul planning between depots...

In the process of planning shipments in the NAV, dispatchers are available information about vehicle load, utilization of its bedding, scheduled times and mileage, cost of realization and quantification of transport profitability.

Optimization methods to help minimize mileage, time and cost to reach the required site when planning a route are not a direct part of the NAV.

### Integration with Plantour
For distribution, the system includes integration functionality with external PLANTOUR planning and optimization software from DIGITECH ČR, spol. s r.o. Thanks to this connection, it is possible to design optimal routes for shipments of delivery points based on day-to-day order processing, including taking into account returns. The routes are designed based on current orders and fleet dynamically in a way that is optimal in terms of costs and at the same time meets all the specified restrictions (journey time, vehicle load limit, vehicle equipment requirements, etc.).

## <a name="see-also"></a>See Also 
[AC ProMIS](ac-pm-promis.md)