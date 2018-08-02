---
title: "AC Promis - LDS Request"
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
ms.contentlocale: cs-cz
ms.lasthandoff: 

---


# <a name="ac-pm-lds-request"></a>LDS Request

Most of the tasks of transport and warehouse operations are based on data provided by business partners. Because each partner has specific communication and the number of partners is not limited, the following principle has been chosen:
 
1. Features for communicating with customer systems.
2. Separate exchangeable message exchange database.
3. MS Dynamics NAV takes data from an exchangeable database and then processes and stores it in internal structures. It also creates new records in an exchangeable database as a basis for outgoing communications towards business partners.

You can interact with partners with the following interactions:

#### Incoming messages from partners
- Warehouse cards
- Insertion order
- Order to pick-up - with shipping
- Order to pick-up - Personal collection
- Scheduled collection
- Changing status
- Unblocking shipments
- Just to the right (without stock operation)
#### Outgoing messages to partners
- Stock status
- Status change (invoked by us)
- Inventory issue
- Inventory income
- Unplanned transport
- Track and Trace

## <a name="see-also"></a>See Also 
[AC ProMIS](ac-pm-promis.md)
