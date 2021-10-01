
TpStage 	|type 				| remark
	-		|-					|-
id			| int 				| PK
name 		| varchar(40) 		| 
status 		| enum ['0','1'] 	| as select '1'
createdBy 	| int 				| FK
createdOn 	| date 				|
editedBy 	| int 				| FK
editedOn 	| date 				|


Tps 		| type 				| remark
	-		|		-			|-
id 			| int 				| PK
no 			| varchar(10) 		|
name 		| varchar(50) 		|
authority 	| int 				| FK
stage 		| int 				| FK
status 		| enum ['0','1'] 	| as select '1'
createdBy 	| int 				| FK
createdOn 	| date 				|
editedBy 	| int 				| FK
editedOn 	| date 				|



TpsStage 	| type 				| remark
	-		|-					|-
id 			| int 				| PK
tpsName 	| int 				| FK
tpStage 	| int 				| FK
changeDate 	| date				|
changeRemark| longtext			|
editedBy 	| int 				| FK
editedOn 	| date 				|


TpsVillage 	| type 				| remark
	-		|-					|-
id 			| int 				| PK
tpsId 		| int 				| FK
villageId 	| int 				| FK


Village			| type 				| remark
	-			|-					|-
id				| int				| PK
name 			| varchar(40)		|
taluka			| int				| FK
district		| int				| FK
authorityType	| int				| FK
status 			| enum ['0','1'] 	| as select '1'
createdBy 		| int 				| FK
createdOn 		| date 				|
editedBy 		| int 				| FK
editedOn 		| date 				|


VillageAuthority| type 				| remark
	-			| -					| -
id 				| int				| PK
villageID		| int				| FK
authorityID		| int				| FK
validFrom		| date 				|
validTill		| date 				|
createdBy 		| int 				| FK
createdOn 		| date 				|
editedBy 		| int 				| FK
editedOn 		| date 				|



AuthorityType 	| type 				| remark
	-			| -					| -
id 				| int				| PK
name			| varchar(50)		| 
status 			| enum ['0','1'] 	| as select '1'
createdBy 		| int 				| FK
createdOn 		| date 				|
editedBy 		| int 				| FK
editedOn 		| date 				|


District 	| type 				| remark
	-		|-					|-
id			| int 				| PK
name		| varchar(40)		|
state		| int				| FK



State	 	| type 				| remark
	-		|-					|-
id			| int 				| PK
name		| varchar(25)		|


Block	 	| type 				| remark
	-		|-					|-
id			| int 				| PK
name		| varchar(50)		|
village		| int				| FK
tpId		| int				| FK
area		| float				| 
jantriRate	| float				|


BlockOwner 		| type 				| remark
	-			|-					|-
id				| int 				| PK
blockId 		| int				| FK
name			| varchar			|
ownershipType	| int				| FK
address			| longtext			| 


OwnershipType	| type 				| remark
	-			|-					|-
id				| int 				| PK
name			| varchar			|
status 			| enum ['0','1'] 	| as select '1'
createdBy 		| int 				| FK
createdOn 		| date 				|
editedBy 		| int 				| FK
editedOn 		| date 				|


Case			| type 				| remark
	-			|-					|-
id				| int 				| PK
caseNo			| int				|
tpsId			| int				| FK


OP				| type 				| remark
	-			|-					|-
id				| int 				| PK
caseId 			| int				| FK
createdBy 		| int 				| FK
createdOn 		| date 				|
editedBy 		| int 				| FK
editedOn 		| date 				|


OpRecord		| type 				| remark
	-			|-					|-
id				| int 				| PK
opId 			| int				| FK
blockId 		| int				| FK
blockAreaUsed	| float 			| 
blockValue 		| float 			|
valueWOConst	| float				| 
valueOfConst 	| float 			|
valueWConst		| float 			|


FP 				| type 				| remark
	-			|-					|-
id 				| int 				|
fpId 			| int				|
createdBy 		| int 				| FK
createdOn 		| date 				|
editedBy 		| int 				| FK
editedOn 		| date 				|


FpRecord 			| type 				| remark
	-				|-					|-
id 					| int				|
fpId 				| int				|
opId 				| int				|
opAreaUsed 			| float 			|
opValue 			| float 			|
valueWOConst		| float				| 
valueOfConst 		| float 			|
valueWConst			| float 			|
roadFactor			| int				|
cornerFactor	 	| int				|
reservationFactor	| int 				|
generalFactor		| int				|
finalValue			| float 			|
vuawoconstruct		| float 			|
vuawconstruct		| float				|



RoadWidth 			| type 				| remark
	-				|-					|-
id 					| int				| PK
roadWidth			| varchar(3)		|
tpId				| int				|
status 				| enum ['0','1'] 	| as select '1'
createdBy 			| int 				| FK
createdOn 			| date 				|
editedBy 			| int 				| FK
editedOn 			| date 				|


Road 			| type 				| remark
	-				|-					|-
id					| int				| PK
roadLength 			| float(10)			|
roadWidthId			| int 				| 
lane				| varchar(3)		|
carpetWidth			| varchar(5)		|
rate				| float(10)			|
cost				| float(20)			|roadLength*rate
createdBy 			| int 				| FK
createdOn 			| date 				|
editedBy 			| int 				| FK
editedOn 			| date 				|



streetLight			| type 				| remark
	-				|-					|-
id					| int				| PK
roadWidthId			| int 				| FK
poleDistance		| varchar(3)		|
totalPole			| varchar(5)		|= poleDistance X roadLength 
rate				| float(10)			|
cost				| float(20)			|= totalPole X rate
createdBy 			| int 				| FK
createdOn 			| date 				|
editedBy 			| int 				| FK
editedOn 			| date 				|



Drainage			| type 				| remark
	-				|-					|-
id					| int				| PK
roadWidthId			| int				| FK
pipeSize			| varcahr(7)		|
rate				| float				|
cost				| float				|= roadLength X rate
createdBy 			| int 				| FK
createdOn 			| date 				|
editedBy 			| int 				| FK
editedOn 			| date 				|



WaterLine			| type 				| remark
	-				|-					|-
id					| int				| PK
roadWidthId			| int				| FK
pipeSize			| varcahr(7)		|
wastagePer	 		| float				|
wastage 			| float				| = roadLength +(pipeSize X wastagePer
rate				| float				|
cost				| float				|= roadLength X rate
createdBy 			| int 				| FK
createdOn 			| date 				|
editedBy 			| int 				| FK
editedOn 			| date 				|



StormWaterDrainage	| type 				| remark
	-				|-					|-
id					| int				| PK
roadWidthId			| int				| FK
pipeSize			| varcahr(7)		|
rate				| float				|
cost				| float				|= roadLength X rate
createdBy 			| int 				| FK
createdOn 			| date 				|
editedBy 			| int 				| FK
editedOn 			| date 				|


