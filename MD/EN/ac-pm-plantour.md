---
title: "AC Promis - Integration Plantour"
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


# <a name="ac-pm-plantour"></a>Integration Plantour

Integration with Plantour is based on MS SQL exchange tables.

The following 4 tables are exported from the NAV:

- **Vehicles** - Vehicle parameters (12-digit code) are also recorded for comparison with delivery point restrictions (see next point)
- **Delivery points** - This list is continuously updated from the NAV as they are created on a regular basis on the documents. There are up to 2 time windows for 7 days a week, followed by vehicle restrictions (maximum weight, folding ramp, loading hand, ... this is customer implementation)
- **Consignments** - there are flows to / from delivery points (commodities but also pallets); Plantour takes care of everything to be done at every moment.
- **Drivers** - only basic codebook for own drivers Code, name, phone, Active

The following 2 tables are imported into the NAV:

- T_TRS_O - calculated routes
- T_ZAST_O - stops on the route

The current way of picking shipments to Plantour is done through filters where the field can be used as the first or last distr number. location, required loading / unloading time, planting status, Plantour status. These filters can be used to select delivery shipments at Plantour scheduling, shipments to date, shipments unplanned, shipments not sent to Plantour.

## <a name="see-also"></a>See Also
[AC ProMIS](ac-pm-promis.md)