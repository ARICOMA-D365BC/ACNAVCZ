---
title: "AC Promis - General texts"
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


# <a name="ac-pm-general-texts"></a>General texts

General texts allow you to define general text one at a time, and then use it in several places in the system. This is the N:N session. There may be N text for one entity, or 1 text may be used by N entities. They can also serve as a template for accompanying texts. For better clarity, you can divide them into groups. General texts are defined in 1 place, directly in the General texts. They consist of a header (code identification) and language variants of texts. The other entities then only join or serve as a template for the definition of the accompanying text.

They are used as notes and also in reports.

### **Codes of use**

Usage codes allow you to scale texts that then connect to different entities.

General texts are displayed in the Info panel of the given entity if at least one general text use is defined for the entity in **General Text Settings**. Clicking on the "Number" field (even in the case of a blank value) the user gets into the general text content. For a given entity, the user can only select from a defined defined list of general texts and join it to the entity. Can not change the content of general text for the entity.

**General text settings** - This is a user-defined codebook that specifies for which entity generic texts will be accessible and with which usage codes. The value in the "Order of Selection" field determines in which order the general text use codes will be offered to users within the same entity.

## <a name="see-also"></a>See Also  
[AC ProMIS](ac-pm-promis.md)