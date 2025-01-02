## Tenants

Concept of Acquiring Tenant when several companies shares the same platform.
Tenant is a container of segregated data.

A payment company requirer : 
- a scheme licence
- acquiring license
because acquiring company gets data from scheme. and pushes money to merchant bank.



The motivation : 

Tenant is dependent of the business model/process
- parameters that define the business process 
- different regulations.

Business models : 
- ex. workflow ( acceptance protocol, ...)
- Clearing configuration (BINs, scheme MIDs)
- reporting structure

Involved applications :
- RICOS (AML/KYC) - because of strict segregation of merchants
- Acquiring : 
	- PASS
	- Dispute
	- Fraud
	- Front Office
- OnBoarding
- Sales
- Acceptance : Shall be agnostic of tenant (EP2, WLOP)

Question : Payment license is linked to one company?
- Payment license : 1 liability, 1 legal entity, ...
- 1 license can concern several european countries but a company reports to one country.

Tenant funcions architecture : shall all be the same.

## Profit center : 
A container of a merchant or Payment Facilitator
more countries or benefit structure sharing the same config.
Motivation : decompose tenant in more observable P&Ls
extended on the wich to share common parameterization.

- per RB country - segregate P&L
- profit center for GSV : 1 per key account
	- same business model. 


### Payment facilitator
it is a collector (collect cards) from the viewpoint of an acquirer.
Allow to have a PF at the top and merchant hierarchies below.
It means : 
- you can have a hierarchy : PF Id -> Merchant Id -> Sub Merchant ID
- a Payment facilitator (and its merchants) in a **profit center**.
See additionnal use cases in Marthe file.
