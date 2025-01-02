#Bauhaus
#WomanEmpowerment 

Outil Complex Adaptive System (CAS)
-> AWESOME

Anatomy de l'Empowerment : 3 domaines dominants 
- Internes : "Power withing", self 
- Relational/Interactional : "Power With", Ressources dispo, contexte intitutionnel
- Comportemental : "power to", Achievement of choices, Acces aux ressources

---
Context
```mermaid
classDiagram

bank --> woman_group : money
bank : contact_group()
bank : total_fund
ONG --> woman_group : money, knowledge, promote entrepreneuship
ONG --> ressources
Company --> woman_group : money, knowledge

limitation_factor --> empowerment : impacts
limitation_factor : caste
limitation_factor : education_system
limitation_factor : group conflict
limitation_factor : house conflict
limitation_factor : small size of the group

improvement_factor --> empowerment
improvement_factor : financial independance
improvement_factor : entrepreneurship
improvement_factor : autonomousloan management
improvement_factor : neighbour group improvement (the bigger, the better)

woman_group --> woman_group : cluster
woman_group : funds
woman_group : asset[]
woman_group : woman[]
woman_group : leader
woman_group : group_knowledge
woman_group : group_self_management()
woman_group : ambiance
woman_group : culture
woman_group : empowerment factor
woman_group : acquirer_competency()

woman_group --* woman

woman : knowledge
woman : work() can be null
woman : income

family --* woman
family : husband

regulation --> empowerment

empowerment --> woman_group
empowerment : outcome
empowerment : tools
empowerment : performances
empowerment : cost
empowerment --> outcome

outcome : knowledge
outcome : contract a loan
outcome : improve self confidence
outcome : conflict
outcome : internal satisfaction
outcome : global satisfaction

```

---
#actions
- model of forces, limiter
- recenser les méthodes systems thinkings appliquées