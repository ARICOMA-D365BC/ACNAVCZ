---
title: "AC Promis - Map&Guide"
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


# <a name="ac-pm-MG"></a>Map&Guide

This communication is only possible with Map & Guide licensed as Server (Desktop edition is not applicable for integration). Communication is then implemented through the following three web services:

- **xLocate** - A NAV is sent to the coordinates and the M&G server returns what is in the given location; and conversely
- **xMap** - NAVs are sent to desired points of interest, and the M&G server returns the map (as a picture) with the marked points.
- **xRoute** - A request for a start and end route is sent from the NAV, the M&G server returns the route represented by the points of departure

Note: In the case of communication with an external server, it is not possible to define custom icons for marking points of interest, only predefined can be used.

## <a name="see-also"></a>See Also
[AC ProMIS](ac-pm-promis.md)