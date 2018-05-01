---
    title: "Spa solution"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Data Rights

Data rights are used to delimit the access to specific data values (e.g., to specific locations, cash registers, centres, etc.). May be allocated to users or groups of users with the permission to assign rights to data.
Can be defined in two ways. Defined value to evaluate the rights either includes or excludes. This will facilitate the definition, the user can choose how to score from short enumeration values. How to evaluate the field specifies the "allocation type", which can take the values:
-	Include
-	Exclude

The field "method of evaluation" determines what is evaluated. Can have the values:
-	Without a value – use for cases where they do not require specific values, but only the existence of the right, for example. Admin rights and run some functionality or report. When the allocation of the rights to the user or group of users is automatically selected the "valid for all values".
-	The value of the field-value is defined evaluates to a table field.
-	Dimensions-value evaluates to a defined "dimension code", for a defined source code. The definition is carried out through actions "Create rights to the dimension" in the Ribbon.
-	Reference table number-this value is used for the child table (for example, for the accompanying lyrics). The definition is carried out through the action of "Create the right to reference data" in the Ribbon.
-	The value group – this method of evaluation is used for each combination of values.

Identification of individual data rights on the customer may designate. What "code" is used for what functionality withe setIt in table The permission settings on the data. This table is used to assign specific rights to data codes to each of the purposes of use, like you set up source codes. 



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)