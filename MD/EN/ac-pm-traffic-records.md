---
title: "AC Promis - Traffic Records"
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


# <a name="ac-pm-traffic-records"></a>Traffic Records

Ancillary evidence for freight traffic is a record of vehicle operations (trailer) where actual journeys and their course are recorded. The record contains data such as handling the vehicle during its operation, the identification of the driver or crew performing the journey, the state of the tachometer, the start and end times of the tank, the places and times of the loading and unloading, the kilometers traveled or the fuel consumption. Evidence based on tank status, mileage, and fueling amount recorded during the journey, allows the vehicle to be quan- tified for a single traffic record.

Data collection on the course of the ride can be either paper records or electronic data capture from the vehicle monitoring device. Standard forms such as ET220 are used for paper records and the driver fills the form during the journey. If electronic records are required, data is manually transferred to vehicle traffic records in the NAV. One of the benefits of this recording method is to accurately determine the beginning and end of a particular vehicle record as it is based on the data in the completed form. Another advantage is the possibility of adding / correcting data when transcribed.

On the other hand, the electronic processing of records based on data downloaded from the vehicle monitoring system depends to a large extent on the quality of the data entered on the operations performed by the driver during the transport operation. For electronic creation of a vehicle traffic record, multiple sources of information are used, which are stored in terminal items, vehicle activity items, border crossing items and refueling items. The disadvantage of electronic processing is the exact determination of the beginning and end of the record, unless it is part of the data from the monitoring device.

A vehicle traffic record is not primarily intended for calculating a driver's entitlement. This calculation is carried out in the separate accounts of Employee Travel Accounts, see chapter below.

Records of vehicle traffic records in the IS provide control tools to verify the accuracy of data between two follow-up vehicle records eg missing traffic records, tachometer status, vehicle consumption.

## <a name="see-also"></a>See Also 
[AC ProMIS](ac-pm-promis.md)