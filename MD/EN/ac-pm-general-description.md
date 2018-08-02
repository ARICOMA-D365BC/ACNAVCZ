---
title: "AC Promis - General Description"
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


# <a name="ac-pm-general-description"></a>General Description

The general descriptions both broaden the standard texts used in the system, for example, into billing lines, and define any general texts that can then be used for various purposes, such as text in the subject of the e-mail, text in the body of the e- mail, addressing.

General descriptions may and may not relate to a particular table. The field from the table can then be used in text syntax. The text can be created from:
- your own text
- field values
- Field name (Headline field)
- system values ​​(working date, current date, current time)
- Registered functions if a function is registered for a given table.

The formula for the text may look like this: Customer% 1% 2% %3 (%4), where the percentage and number represent the defined parameters. Text translations can be defined in different languages. If the Type = field title is used in the formula, its translation is dependent on the implemented language sets of objects.
You can use the Test action to check the shape of a predefined text for the selected entry.

**Codes of Use of General Descriptions** - This is a user-defined codebook that defines the use of general descriptions.

**Setting descriptions** - This structure is used to set up general descriptions in different parts of the spa solution.

## <a name="see-also"></a>See Also 
[AC ProMIS](ac-pm-promis.md)