---
Title: "WorkFlow-Controlled Tables"
Author: AutoCont
Date: 07/31/2018
Product: dynamics-nav-2018
Contentlocale: en
---

# <a name = "ac-pp-workflow-linker-tables.md" > </a> WorkFlow - Controlled Tables

WorkFlow - Controlled Tables add-on module extends the functionality of the WorkFlow module with the possibility of checking records or fields in tables linked with the table which is managed by workflow.
The State of the workflow is then allowed to change only if all the checks in the context of controlled tables match. Practical use can be, for example, this:

* If the workflow is applied to the document with the header and the lines, for example, on a sales order, you can check whether there are any header rows, or rows of some type or content. For example. the order contains at least one row of the goods, or that it has on all lines vyplněnu price or location or glob. dimension, etc.
* You can check the record source to a field in a table with the workflow contains the necessary data in the other fields. If the document header is filled in the salesperson code field, then checks whether the retailer filled with an email.



## <a name = "see-also" > </a>See Also  
[AC Productivity pack](ac-pp-productivity-pack.md)  
