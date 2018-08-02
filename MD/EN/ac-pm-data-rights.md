---
title: "AC Promise - Data Rights"
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


# <a name="ac-pm-data-rights"></a>Data Rights

**Data Rights** is used to define access to specific data values ​​(e.g., specific locations, cash registers, centers, etc.). They can be assigned to users or groups of users who have permission to assign data rights.

They can be defined in two ways. The defined value is either included or excluded. This makes it easier for the user to define, so he can choose the method according to a smaller set of values. The evaluation method determines the "Assignment type" field, which can take the following values:

- Include
- Exclude

The "Evaluation Method" field determines what is being evaluated. It can acquire the following values:

- No value - Use for cases where specific values ​​are not required, but only the existence of a given right, eg admin rights and running some functionality or assembly. When assigning a user or group of users to the right, the field "Valid for all values" is automatically checked.
- Field value - the value of a defined table field is evaluated.
- Dimension value - Defines the "Dimension Code" for the defined Origin Code. The definition is done through the "Create Dimension Rights" action in the Ribbon.
- Reference table number - This value is used for child tables (e.g., for Accompanying Texts). The definition is done through the "Set Reference Rights Rights" action in the ribbon.
- Value Group - This evaluation method is used for value combinations.

The identification of the individual data rights can be determined by the customer. What "Code" is used for what functionality is set in the **Data rights settings table**. This table is used to assign specific data rights codes to individual uses, similar to the Origin Codes.

## <a name="see-also"></a>See Also  
[AC ProMIS](ac-pm-promis.md)