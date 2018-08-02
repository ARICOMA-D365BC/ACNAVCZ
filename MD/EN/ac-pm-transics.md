---
title: "AC Promis - Integration Transics"
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


# <a name="ac-pm-transics"></a>Integration Transics

## TRANSICS
Exchange of Transics data is based on web services. Available web services are implemented:
- Get_Vehicles
- Get_VehicleInfo_On_Date
- Insert_Planning
- Update_Planning
- Get_Planning_Modifications
- Cancel_Planning
- Get_Positions
- Get_ActivityList
- Get_ActivityReportDetail
- Get_RefuelReport
- Get_BorderCrossingReport
- Get_EcoMonitor_Report

The following information is obtained from the above services:
- Vehicle Position Items - This is an informative item for the dispatcher, history is logged
- Daily position - see previous, but throughout the day to add any missing information (for example, the service was unavailable for some time)
- Border Crossing Items - This information serves as ancillary data for billing of travel orders
- Refueling items - These are informative data as the driver has noticed that he has refilled
- Ecomonitor entry - information on driving mode; serves as a basis for reporting or customer solutions for driver evaluation
- Transics Activity Items - in combination with Border Crossings, the data in the Driver Activity Log is generated, which is the primary result of the entire integration.

    These are the following types of activities:

- Consultation - Depending on the specific instruction, eg that he started to interpret, dispose
- Extra Information - Additional information to be entered by the driver (according to a specific instruction set, it must be modified as a customization
- Anomaly
- Mistakes

## <a name="see-also"></a>See Also
[AC ProMIS](ac-pm-promis.md)