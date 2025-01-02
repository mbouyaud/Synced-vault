

Definition of an Actor model : 

ticket/an order/an organisation triger

Information : 
- shall be multiplexed
- follow a communication channel

An actor receives from a perception tool : 
- ticket
- information
Produces : 
- ticket 
- information
- action on the system

```mermaid
C4Context
title Enterprise information flow

Person(PO, "PO of sys A", "Receives a ticket from PM, design, provides spec to dev.") {
	input(JiraPO,"Jira ticket received by PM")
	input(information,"Information from system")
	Output(JiraDev,"Jira ticket raised to Dev")
	
}

Role(Dev, "PO of sys A", "Receives a ticket from PO, delivers and test.")
{
	input(JiraDel,"Jira ticket received by PO")
	input(information,"Information from system")
	Output(System,"delivery of system")
	
}

Rel(PO, Dev, "Sends e-mails")

```
