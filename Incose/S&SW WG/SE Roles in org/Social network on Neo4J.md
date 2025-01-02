#SSWWG 
#INCOSE 
#Neo4j
#graph_model

source [social network tuto](https://github.com/thobe/social-network-workshop#shell)

Easy graph construction tool https://neo4j.com/docs/getting-started/current/data-modeling/data-modeling-tools/


- [x] Installation of JDK
- [x] Installation Maven
- [ ] Basic Neo4j [Neo4j entry points](https://neo4j.com/docs/getting-started/current/get-started-with-neo4j/graph-database/)
	- [ ] Aura DB : passwd a0ho0oA3FE2wea5X_37fVjZMJJir4otP2MDst9s-sDw
	- [ ] Aura allows to play with import
- [x] Creation of first patters without without SE
- [x] Update first pattern with SE
- [x] Creation of primary patterns
	- [x] process
	- [x] roles
	- [x] links
		- [x] before and after
- [x] Instantiation of John example
- [ ] [[Create a shared workspace]]
- [ ] Creation of a DBMS
	- [ ] en local
	- [ ] SE Role, passwrd : Sirius397
- [ ] 
- [ ] 

# first role pattern

Pattern model : arrow.app
-> Sauvé sur mon google drive. mbouyaud@gmail.com
![[SE Roles exploration.png]]

json description [SE role exploration](file :////Users/mbouyaud/Downloads/SE Roles exploration.json)


## CREATE query

CREATE (n8:O {full_role: "Operator", project: "null", SAFE_Role: "yes"})-[:R {type: "process", `without SE`: "yes"}]->(:OPER {full_name_process: "Operation", type: "process_15288"})<-[:i {`without SE`: "yes"}]-(n3:PO {full_role: "product owner", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(VAL:VAL {full_name_process: "Validation ", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1:PM {full_role: "Product Management", project: "null", SAFE_Role: "yes"})-[:r {type: "process", `without SE`: "yes"}]->(:TRANS {full_name_process: "Transition", type: "process_15288"})<-[:a {`without SE`: "yes"}]-(:BO {full_role: "business owner", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(:BMA {full_name_process: "Business or Misson Analysis", type: "process_15288"}),
(SRD:SRD {full_name_process: "System Requirement Processs", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1)-[:a {type: "process", `without SE`: "yes"}]->(SNRD:SNRD {full_name_process: "Stakeholder needs & requirement definition", type: "process_15288"})<-[:r {`without SE`: "yes"}]-(n3)-[:r {`without SE`: "yes"}]->(SRD),
(VAL)<-[:c {type: "process", `without SE`: "yes"}]-(n8)-[:c {type: "process", `without SE`: "yes"}]->(SNRD)<-[:c {type: "process", `without SE`: "yes"}]-(:M {full_role: "Maintainer", project: "null", SAFE_Role: "yes"})-[:R {type: "process", `without SE`: "yes"}]->(MAINT:MAINT {full_name_process: "Maintenance", type: "process_15288"}),
(DD:DD {full_name_process: "Design Definition", type: "process_15288"})<-[:R {`without SE`: "yes"}]-(n3)-[:a {`without SE`: "yes"}]->(:AD {full_name_process: "Architecture Definition", type: "process_15288"})<-[:r {`without SE`: "yes"}]-(n5:AT {full_role: "Agile Team", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(SA:SA {full_name_process: "System Analysis Process", type: "process_15288"}),
(n3)-[:r {type: "process", `without SE`: "yes"}]->(:DIS {full_name_process: "Disposal", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1)-[:A {type: "process", `without SE`: "yes"}]->(DD),
(VER:VER {full_name_process: "Verification ", type: "process_15288"})<-[:R {`without SE`: "yes"}]-(n5)-[:R {`without SE`: "yes"}]->(INT:INT {full_name_process: "integration", type: "process_15288"})<-[:C {`without SE`: "yes"}]-(n4:SM {full_role: "Scrum Master", project: "null", SAFE_Role: "yes"})-[:C {`without SE`: "yes"}]->(IMP:IMP {full_name_process: "Implementation", type: "process_15288"})<-[:A {`without SE`: "yes"}]-(n3)-[:a {`without SE`: "yes"}]->(SA),
(VAL)<-[:i {`without SE`: "yes"}]-(n5)-[:R {`without SE`: "yes"}]->(IMP),
(n4)-[:C {`without SE`: "yes"}]->(VER)<-[:A {`without SE`: "yes"}]-(n3)-[:A {`without SE`: "yes"}]->(INT),
(n3)-[:I {`without SE`: "yes"}]->(MAINT),
(:SE {full_role: "System Engineer", project: "null"}),
(:`IV&V` {full_role: "IV&V", project: "null"}),
(:LS {full_role: "Logistic Support", project: "null", SAFE_Role: "yes"})

## Merge query

MERGE (n8:O {full_role: "Operator", project: "null", SAFE_Role: "yes"})-[:R {type: "process", `without SE`: "yes"}]->(:OPER {full_name_process: "Operation", type: "process_15288"})<-[:i {`without SE`: "yes"}]-(n3:PO {full_role: "product owner", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(VAL:VAL {full_name_process: "Validation ", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1:PM {full_role: "Product Management", project: "null", SAFE_Role: "yes"})-[:r {type: "process", `without SE`: "yes"}]->(:TRANS {full_name_process: "Transition", type: "process_15288"})<-[:a {`without SE`: "yes"}]-(:BO {full_role: "business owner", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(:BMA {full_name_process: "Business or Misson Analysis", type: "process_15288"})
MERGE (SRD:SRD {full_name_process: "System Requirement Processs", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1)-[:a {type: "process", `without SE`: "yes"}]->(SNRD:SNRD {full_name_process: "Stakeholder needs & requirement definition", type: "process_15288"})<-[:r {`without SE`: "yes"}]-(n3)-[:r {`without SE`: "yes"}]->(SRD)
MERGE (VAL)<-[:c {type: "process", `without SE`: "yes"}]-(n8)-[:c {type: "process", `without SE`: "yes"}]->(SNRD)<-[:c {type: "process", `without SE`: "yes"}]-(:M {full_role: "Maintainer", project: "null", SAFE_Role: "yes"})-[:R {type: "process", `without SE`: "yes"}]->(MAINT:MAINT {full_name_process: "Maintenance", type: "process_15288"})
MERGE (DD:DD {full_name_process: "Design Definition", type: "process_15288"})<-[:R {`without SE`: "yes"}]-(n3)-[:a {`without SE`: "yes"}]->(:AD {full_name_process: "Architecture Definition", type: "process_15288"})<-[:r {`without SE`: "yes"}]-(n5:AT {full_role: "Agile Team", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(SA:SA {full_name_process: "System Analysis Process", type: "process_15288"})
MERGE (n3)-[:r {type: "process", `without SE`: "yes"}]->(:DIS {full_name_process: "Disposal", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1)-[:A {type: "process", `without SE`: "yes"}]->(DD)
MERGE (VER:VER {full_name_process: "Verification ", type: "process_15288"})<-[:R {`without SE`: "yes"}]-(n5)-[:R {`without SE`: "yes"}]->(INT:INT {full_name_process: "integration", type: "process_15288"})<-[:C {`without SE`: "yes"}]-(n4:SM {full_role: "Scrum Master", project: "null", SAFE_Role: "yes"})-[:C {`without SE`: "yes"}]->(IMP:IMP {full_name_process: "Implementation", type: "process_15288"})<-[:A {`without SE`: "yes"}]-(n3)-[:a {`without SE`: "yes"}]->(SA)
MERGE (VAL)<-[:i {`without SE`: "yes"}]-(n5)-[:R {`without SE`: "yes"}]->(IMP)
MERGE (n4)-[:C {`without SE`: "yes"}]->(VER)<-[:A {`without SE`: "yes"}]-(n3)-[:A {`without SE`: "yes"}]->(INT)
MERGE (n3)-[:I {`without SE`: "yes"}]->(MAINT)
MERGE (:SE {full_role: "System Engineer", project: "null"})
MERGE (:`IV&V` {full_role: "IV&V", project: "null"})
MERGE (:LS {full_role: "Logistic Support", project: "null", SAFE_Role: "yes"})

## MATCH query

MATCH path0 = (n8:O {full_role: "Operator", project: "null", SAFE_Role: "yes"})-[:R {type: "process", `without SE`: "yes"}]->(:OPER {full_name_process: "Operation", type: "process_15288"})<-[:i {`without SE`: "yes"}]-(n3:PO {full_role: "product owner", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(VAL:VAL {full_name_process: "Validation ", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1:PM {full_role: "Product Management", project: "null", SAFE_Role: "yes"})-[:r {type: "process", `without SE`: "yes"}]->(:TRANS {full_name_process: "Transition", type: "process_15288"})<-[:a {`without SE`: "yes"}]-(:BO {full_role: "business owner", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(:BMA {full_name_process: "Business or Misson Analysis", type: "process_15288"}),
path1 = (SRD:SRD {full_name_process: "System Requirement Processs", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1)-[:a {type: "process", `without SE`: "yes"}]->(SNRD:SNRD {full_name_process: "Stakeholder needs & requirement definition", type: "process_15288"})<-[:r {`without SE`: "yes"}]-(n3)-[:r {`without SE`: "yes"}]->(SRD),
path2 = (VAL)<-[:c {type: "process", `without SE`: "yes"}]-(n8)-[:c {type: "process", `without SE`: "yes"}]->(SNRD)<-[:c {type: "process", `without SE`: "yes"}]-(:M {full_role: "Maintainer", project: "null", SAFE_Role: "yes"})-[:R {type: "process", `without SE`: "yes"}]->(MAINT:MAINT {full_name_process: "Maintenance", type: "process_15288"}),
path3 = (DD:DD {full_name_process: "Design Definition", type: "process_15288"})<-[:R {`without SE`: "yes"}]-(n3)-[:a {`without SE`: "yes"}]->(:AD {full_name_process: "Architecture Definition", type: "process_15288"})<-[:r {`without SE`: "yes"}]-(n5:AT {full_role: "Agile Team", project: "null", SAFE_Role: "yes"})-[:r {`without SE`: "yes"}]->(SA:SA {full_name_process: "System Analysis Process", type: "process_15288"}),
path4 = (n3)-[:r {type: "process", `without SE`: "yes"}]->(:DIS {full_name_process: "Disposal", type: "process_15288"})<-[:a {type: "process", `without SE`: "yes"}]-(n1)-[:A {type: "process", `without SE`: "yes"}]->(DD),
path5 = (VER:VER {full_name_process: "Verification ", type: "process_15288"})<-[:R {`without SE`: "yes"}]-(n5)-[:R {`without SE`: "yes"}]->(INT:INT {full_name_process: "integration", type: "process_15288"})<-[:C {`without SE`: "yes"}]-(n4:SM {full_role: "Scrum Master", project: "null", SAFE_Role: "yes"})-[:C {`without SE`: "yes"}]->(IMP:IMP {full_name_process: "Implementation", type: "process_15288"})<-[:A {`without SE`: "yes"}]-(n3)-[:a {`without SE`: "yes"}]->(SA),
path6 = (VAL)<-[:i {`without SE`: "yes"}]-(n5)-[:R {`without SE`: "yes"}]->(IMP),
path7 = (n4)-[:C {`without SE`: "yes"}]->(VER)<-[:A {`without SE`: "yes"}]-(n3)-[:A {`without SE`: "yes"}]->(INT),
path8 = (n3)-[:I {`without SE`: "yes"}]->(MAINT),
path9 = (:SE {full_role: "System Engineer", project: "null"}),
path10 = (:`IV&V` {full_role: "IV&V", project: "null"}),
path11 = (:LS {full_role: "Logistic Support", project: "null", SAFE_Role: "yes"})
RETURN path0, path1, path2, path3, path4, path5, path6, path7, path8, path9, path10, path11

# With SE
## CREATE
CREATE (n24:SPE {full_role: "Specialty Engineer", project: "null", SAFE_Role: "no"})-[:C {with_SE: "yes"}]->(DIS:DIS {full_name_process: "Disposal", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n0:BO {full_role: "business owner", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(BMA:BMA {full_name_process: "Business or Misson Analysis", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n0)-[:I {with_SE: "yes"}]->(VAL:VAL {full_name_process: "Validation ", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n1:PM {full_role: "Product Management", project: "null", SAFE_Role: "yes"})-[:I {with_SE: "yes"}]->(DIS)<-[:A {with_SE: "yes"}]-(n2:SE {full_role: "System Engineer", project: "null", SAFE_Role: "no"}),
(SRD:SRD {full_name_process: "System Requirement Processs", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n3:PO {full_role: "product owner", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(SNRD:SNRD {full_name_process: "Stakeholder needs & requirement definition", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(BMA),
(n6:`IV&V` {full_role: "IV&V", project: "null", SAFE_Role: "no"})-[:R {with_SE: "yes"}]->(VAL)<-[:C {with_SE: "yes"}]-(n3)-[:C {with_SE: "yes"}]->(SA:SA {full_name_process: "System Analysis Process", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(AD:AD {full_name_process: "Architecture Definition", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(SRD)<-[:C {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(SNRD)<-[:C {with_SE: "yes"}]-(n8:O {full_role: "Operator", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(TRANS:TRANS {full_name_process: "Transition", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n9:M {full_role: "Maintainer", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(VAL),
(MAINT:MAINT {full_name_process: "Maintenance", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n9)-[:C {with_SE: "yes"}]->(SNRD),
(n5:AT {full_role: "Agile Team", project: "null", SAFE_Role: "yes"})-[:R {with_SE: "yes"}]->(INT:INT {full_name_process: "integration", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n4:SM {full_role: "Scrum Master", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(IMP:IMP {full_name_process: "Implementation", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(SRD)<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(AD)<-[:C {with_SE: "yes"}]-(n5)-[:C {with_SE: "yes"}]->(SA),
(SA)<-[:A {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(DD:DD {full_name_process: "Design Definition", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(VER:VER {full_name_process: "Verification ", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n4),
(n8)-[:R {with_SE: "yes"}]->(:OPER {full_name_process: "Operation", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n3)-[:R {with_SE: "yes"}]->(DD),
(n6)-[:R {with_SE: "yes"}]->(VER)<-[:A {with_SE: "yes"}]-(n2)-[:A {with_SE: "yes"}]->(INT)<-[:I {with_SE: "yes"}]-(n1)-[:I {with_SE: "yes"}]->(IMP)<-[:R {with_SE: "yes"}]-(n5),
(n3)-[:I {with_SE: "yes"}]->(MAINT)<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(VAL)<-[:A {with_SE: "yes"}]-(n2)-[:A {with_SE: "yes"}]->(TRANS)<-[:I {with_SE: "yes"}]-(n1)-[:I {with_SE: "yes"}]->(VER),
(DIS)<-[:R {with_SE: "yes"}]-(:LS {full_role: "Logistic Support", project: "null", SAFE_Role: "yes"})-[:R {with_SE: "yes"}]->(TRANS),
(n8)-[:C {with_SE: "yes"}]->(VAL)

## MATCH
MATCH path0 = (n24:SPE {full_role: "Specialty Engineer", project: "null", SAFE_Role: "no"})-[:C {with_SE: "yes"}]->(DIS:DIS {full_name_process: "Disposal", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n0:BO {full_role: "business owner", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(BMA:BMA {full_name_process: "Business or Misson Analysis", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n0)-[:I {with_SE: "yes"}]->(VAL:VAL {full_name_process: "Validation ", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n1:PM {full_role: "Product Management", project: "null", SAFE_Role: "yes"})-[:I {with_SE: "yes"}]->(DIS)<-[:A {with_SE: "yes"}]-(n2:SE {full_role: "System Engineer", project: "null", SAFE_Role: "no"}),
path1 = (SRD:SRD {full_name_process: "System Requirement Processs", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n3:PO {full_role: "product owner", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(SNRD:SNRD {full_name_process: "Stakeholder needs & requirement definition", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(BMA),
path2 = (n6:`IV&V` {full_role: "IV&V", project: "null", SAFE_Role: "no"})-[:R {with_SE: "yes"}]->(VAL)<-[:C {with_SE: "yes"}]-(n3)-[:C {with_SE: "yes"}]->(SA:SA {full_name_process: "System Analysis Process", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(AD:AD {full_name_process: "Architecture Definition", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(SRD)<-[:C {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(SNRD)<-[:C {with_SE: "yes"}]-(n8:O {full_role: "Operator", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(TRANS:TRANS {full_name_process: "Transition", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n9:M {full_role: "Maintainer", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(VAL),
path3 = (MAINT:MAINT {full_name_process: "Maintenance", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n9)-[:C {with_SE: "yes"}]->(SNRD),
path4 = (n5:AT {full_role: "Agile Team", project: "null", SAFE_Role: "yes"})-[:R {with_SE: "yes"}]->(INT:INT {full_name_process: "integration", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n4:SM {full_role: "Scrum Master", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(IMP:IMP {full_name_process: "Implementation", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(SRD)<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(AD)<-[:C {with_SE: "yes"}]-(n5)-[:C {with_SE: "yes"}]->(SA),
path5 = (SA)<-[:A {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(DD:DD {full_name_process: "Design Definition", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(VER:VER {full_name_process: "Verification ", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n4),
path6 = (n8)-[:R {with_SE: "yes"}]->(:OPER {full_name_process: "Operation", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n3)-[:R {with_SE: "yes"}]->(DD),
path7 = (n6)-[:R {with_SE: "yes"}]->(VER)<-[:A {with_SE: "yes"}]-(n2)-[:A {with_SE: "yes"}]->(INT)<-[:I {with_SE: "yes"}]-(n1)-[:I {with_SE: "yes"}]->(IMP)<-[:R {with_SE: "yes"}]-(n5),
path8 = (n3)-[:I {with_SE: "yes"}]->(MAINT)<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(VAL)<-[:A {with_SE: "yes"}]-(n2)-[:A {with_SE: "yes"}]->(TRANS)<-[:I {with_SE: "yes"}]-(n1)-[:I {with_SE: "yes"}]->(VER),
path9 = (DIS)<-[:R {with_SE: "yes"}]-(:LS {full_role: "Logistic Support", project: "null", SAFE_Role: "yes"})-[:R {with_SE: "yes"}]->(TRANS),
path10 = (n8)-[:C {with_SE: "yes"}]->(VAL)
RETURN path0, path1, path2, path3, path4, path5, path6, path7, path8, path9, path10

## MERGE

MERGE (n24:SPE {full_role: "Specialty Engineer", project: "null", SAFE_Role: "no"})-[:C {with_SE: "yes"}]->(DIS:DIS {full_name_process: "Disposal", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n0:BO {full_role: "business owner", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(BMA:BMA {full_name_process: "Business or Misson Analysis", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n0)-[:I {with_SE: "yes"}]->(VAL:VAL {full_name_process: "Validation ", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n1:PM {full_role: "Product Management", project: "null", SAFE_Role: "yes"})-[:I {with_SE: "yes"}]->(DIS)<-[:A {with_SE: "yes"}]-(n2:SE {full_role: "System Engineer", project: "null", SAFE_Role: "no"})
MERGE (SRD:SRD {full_name_process: "System Requirement Processs", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n3:PO {full_role: "product owner", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(SNRD:SNRD {full_name_process: "Stakeholder needs & requirement definition", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(BMA)
MERGE (n6:`IV&V` {full_role: "IV&V", project: "null", SAFE_Role: "no"})-[:R {with_SE: "yes"}]->(VAL)<-[:C {with_SE: "yes"}]-(n3)-[:C {with_SE: "yes"}]->(SA:SA {full_name_process: "System Analysis Process", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(AD:AD {full_name_process: "Architecture Definition", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(SRD)<-[:C {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(SNRD)<-[:C {with_SE: "yes"}]-(n8:O {full_role: "Operator", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(TRANS:TRANS {full_name_process: "Transition", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n9:M {full_role: "Maintainer", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(VAL)
MERGE (MAINT:MAINT {full_name_process: "Maintenance", type: "process_15288"})<-[:R {with_SE: "yes"}]-(n9)-[:C {with_SE: "yes"}]->(SNRD)
MERGE (n5:AT {full_role: "Agile Team", project: "null", SAFE_Role: "yes"})-[:R {with_SE: "yes"}]->(INT:INT {full_name_process: "integration", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n4:SM {full_role: "Scrum Master", project: "null", SAFE_Role: "yes"})-[:C {with_SE: "yes"}]->(IMP:IMP {full_name_process: "Implementation", type: "process_15288"})<-[:A {with_SE: "yes"}]-(n2)-[:R {with_SE: "yes"}]->(SRD)<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(AD)<-[:C {with_SE: "yes"}]-(n5)-[:C {with_SE: "yes"}]->(SA)
MERGE (SA)<-[:A {with_SE: "yes"}]-(n1)-[:A {with_SE: "yes"}]->(DD:DD {full_name_process: "Design Definition", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(VER:VER {full_name_process: "Verification ", type: "process_15288"})<-[:C {with_SE: "yes"}]-(n4)
MERGE (n8)-[:R {with_SE: "yes"}]->(:OPER {full_name_process: "Operation", type: "process_15288"})<-[:I {with_SE: "yes"}]-(n3)-[:R {with_SE: "yes"}]->(DD)
MERGE (n6)-[:R {with_SE: "yes"}]->(VER)<-[:A {with_SE: "yes"}]-(n2)-[:A {with_SE: "yes"}]->(INT)<-[:I {with_SE: "yes"}]-(n1)-[:I {with_SE: "yes"}]->(IMP)<-[:R {with_SE: "yes"}]-(n5)
MERGE (n3)-[:I {with_SE: "yes"}]->(MAINT)<-[:C {with_SE: "yes"}]-(n24)-[:C {with_SE: "yes"}]->(VAL)<-[:A {with_SE: "yes"}]-(n2)-[:A {with_SE: "yes"}]->(TRANS)<-[:I {with_SE: "yes"}]-(n1)-[:I {with_SE: "yes"}]->(VER)
MERGE (DIS)<-[:R {with_SE: "yes"}]-(:LS {full_role: "Logistic Support", project: "null", SAFE_Role: "yes"})-[:R {with_SE: "yes"}]->(TRANS)
MERGE (n8)-[:C {with_SE: "yes"}]->(VAL)