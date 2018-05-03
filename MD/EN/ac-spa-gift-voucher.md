---
    title: "Gift Vouchers"
    author: AutoCont
    ms.date: 04/30/2018
    ms.topic: article
    ms.prod: dynamics-nav-2017
    ms.contentlocale: en
    ms.lasthandoff: 04/30/2018
---

# Gift Vouchers 

## RECORDING
Gift vouchers are recorded in the system on the Tab gift vouchers. The individual cards are numbered automatically based on the number series as defined in the type of gift certificates. Depending on the type are also accessible to the respective functions that can be used with the order of the given type to perform.
Important fields:
-	The amount of the vouchers including VAT – this is the amount to which the certificate relates and for which products will be drawn
-	The sales amount including VAT vouchers – this is the amount for which the DP will be sold. Automatically position the amount from the amount field of the voucher, including VAT, but it can be altered in this field. If will be defined the lower amount, the difference is nominal and the sales value in the sale of the voucher is posted on the new line to the account defined in the Financial discount account sales discount. Konto is defined in the type of discounts, gift certificates, and when a gift certificate is transmitted to the card, gift certificates, and from there to a sales document, if the amount of the voucher is different from the sales amount of the voucher.
-	The base of VAT and the VAT base to be used – show the amount without VAT. In the conclusion of the gift certificate is checked to see whether it is the VAT base to use zero.
-	The amount of services including VAT – this field is filled by the Bills with the posting type = "sales services" as the sum of the prices of services vouchers. The resulting value depends on the value in the date field of the award and the price level defined in gift vouchers.
-	Tax business posting group – is added automatically when the sale of the voucher and to this value is then checks the VAT business posting group in the use of the voucher.
-	Number of employees – is to be filled in for voucher with the posting type = "the gift of the company"
-	The Client/Payer Tab

Each feature on the gift certificates will be made available in the Ribbon or znepřístupňují based on the type of posting.

### Creation of a gift voucher
Gift certificates can be created in several ways, using:
-	Create a new voucher – this function spawns a new gift certificate of the same type as the DP that is the insertion point when creating a new DP
-	Create a new voucher type – allows you to before the establishment of the new DP select the type of the new DP
-	Automatic establishment of a set of vouchers – each DP will establish the formation of automatically

By creating a new voucher voucher number shall be assigned from the number serie defined for that type and make up some of the information from the type of the voucher. For more information, the user fills in the DP.

### Creation of a set of gift vouchers
A set of gift certificates, you can create with the function "Create new set". Nthe memory the number shall be assigned from the number serie defined for that type of information and make up of the type of set. At the same time the individual is set up automatically defined for a set of gift cards. 

### ISSUE/RETURN OF THE GIFT VOUCHER 
Issue and return of the function can be accessed from the tab only for DP gift certificates with the posting type = "the gift of the company". Requires the completed employee number on the DP.
-	**Issue** – establish an entry type sales and allow DP DP use (filled the amount to use, including VAT).
-	**Return** -item type Return spawns a DP and DP.

## SALE
### Sale of a gift vouchers
The sale of gift vouchers with the posting type = value, the sale of services is carried out on the sales document, by using the function "Design sale of gift vouchers". On the sales document, only offers outstanding gift certificates with the posting type Value and sale services, that are not yet sold. The sale will take place at the sales amount including sales tax. If it is different from the nominal value of the vouchers shall be additional sales line discount account defined in the type of the voucher with the differential amount.
Posting a sales document
-	a DP item type sale on the nominal amount of the voucher that appears on credit vouchers. If you are selling discount was applied, the discount amount goes to the discount.  
-	The value in the Sale to DP changes to Yes
-	Populates the amount to use, including VAT and DP can be used for pumping products

### Cancellation of a gift voucher sale
Cancel the sale of DP is done on a sales credit memo or sales credit memo with the function "saleDesign sale of gift vouchers". On the sales credit memo is only offers outstanding gift certificates with the posting type Value and sale services with non-zero amount for use including VAT.
You post a sales credit memo
-	a DP item type Return on the nominal amount of the voucher that appears on credit vouchers. If you are selling discount was applied, the discount amount is returned to the account of discounts.  
-	The amount to use, including VAT is reset
-	DP is closed

### Sale of a sets of gift vouchers sale
Sale of gift certificates is carried out on the sales document, by using the function "Design sale sets of gift vouchers". It is the only place where he works with as a whole. On the sales document, offers only unclosed and unsold sets of gift vouchers. 
Posting a sales document
-	DP type sale items arise on the face amount of the vouchers 
-	The value in the sales field on each of the DP and DP in the set changes to Yes
-	Populates the amounts to be used, including VAT and individual DP can be used for pumping products

## USAGE
### The usage of gift voucher on the sales document
On the sales document, you can use the open a valid DP with non-zero amount for use including VAT. To use the function:
-	**Connect your gift certificate**  
	- 	The function appends the selected DP in the sales document max. to the amount to use, including VAT
	- 	Used amount of DP is displayed in the drawn amount of gift certificates (the General tab on the sales document). In detail the amounts of the individual DP used attached to the document, it is possible to get a click of this amount, or by using the Assigned gift certificates (Navigation tab in the Ribbon, the sales document).

-	**Cancel the connection gift vouchers**  
	- 	This function cancels all assignments of the DP to the sales document, therefore the field is reset due amount of gift vouchers

-	**Test the connected gift vouchers**  
	- 	This function tests the connection of gift vouchers on the sales document and test result shall be notified to the user. 

Posting a sales document followed by the DP:
-	a DP item type to use for the amount that was used on the document and will be reduced by this amount account DP 
-	The value in the use of the DP is changed to Yes
-	Change the amount to use, including VAT
-	If it's the entire amount, close the gift certificate

## FORFEITURE
Once the gift certificate is no longer valid and has a non-zero balance, it is possible to charge a forfeiture, which will take up the remaining amount from the account to the account of the confiscation of the proceeds of the DP, which is defined in gift vouchers. Confiscation is possible to post from the card or gift certificates by using the features overview:
-	**Post forfeiture**  
	- 	will feature a specific balance of foreclosed from DP to DP account proceeds confiscation
	- 	creates an item type of confiscation of the DP
	- 	Resets the amount to use, including VAT
	- 	closes the DP

-	**Post forfeiture of all expired vouchers** – posts a forfeiture for any expired voucher
-	**Post the cancellation of forfeiture**  
	- 	will feature a specific balance account of the proceeds of the forfeited DP confiscation on account of the DP
	- 	creates an item type of confiscation of the DP with the opposite sign
	- 	populates the amount to use, including VAT
	- 	Open the DP 



## <a name="see-also"></a>See also
[AC Spa solution](ac-spa-solution.md)