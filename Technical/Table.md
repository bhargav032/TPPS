### TpStage
|TpStage 	|type 				| remark 		| description 	|
|	---		|----				|----			| ----			|
|id			| int 				| PK 			| 				|
|name 		| varchar(40) 		| 				| 				|
|status 	| enum ['0','1'] 	| as select '1'	|				|
|createdBy 	| int 				| FK			| User-->id		|
|createdOn 	| date 				|				|				|
|editedBy 	| int 				| FK			| User-->id		|
|editedOn 	| date 				|				|				|


### Tps
|Tps 		| type 				| remark 		| description 	|
|---		|---				|---			| ---			|
|id 		| int 				| PK			|  				|
|no 		| varchar(10) 		|				|				|
|name 		| varchar(50) 		|				|				|
|authority 	| int 				| FK			| Authority-->id |
|stage 		| int 				| FK			| Tpstage-->id	|
|status 	| enum ['0','1'] 	| as select '1'	|				|
|createdBy 	| int 				| FK			| User-->id		|
|createdOn 	| date 				|				|				|
|editedBy 	| int 				| FK			| User-->id		|
|editedOn 	| date 				|				|				|



### TpsStage
|TpsStage 		| type 				| remark 		| description	|
|---			|---				|---			| ---			|
|id 			| int 				| PK			|				|
|tpsName 		| int 				| FK			| Tps-->id		|
|tpStage 		| int 				| FK			| TpStage-->id	|
|changeDate 	| date				|				|				|
|changeRemark	| longtext			|				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				|				|


### TpsVillage
|TpsVillage	| type 				| remark 		| description	|
|	-		|-					|- 				| -				|
|id 		| int 				| PK			|				|
|tpsId 		| int 				| FK			| Tps-->id		|
|villageId 	| int 				| FK			| Village-->id	|


### Village
|Village		| type 				| remark 		| description			|
|	-			|-					|-				| -						|
|id				| int				| PK			|						|
|name 			| varchar(40)		|				|						|
|taluka			| int				| FK			| Taluka-->id			|
|authorityType	| int				| FK			| AuthorityType-->id	|
|status 		| enum ['0','1'] 	| as select '1'	|						|
|createdBy 		| int 				| FK			| User-->id				|
|createdOn 		| date 				|				|						|
|editedBy 		| int 				| FK			| User-->id				|
|editedOn 		| date 				|				| 						|


### Taluka
|Taluka			| type 				| remark 		| description	|
|	-			|-					|-				| -				|
|id				| int				| PK			|				|
|name			| varchar(40)		| 				|				|
|district		| int				| FK 			| District-->id	|
|createdBy 		| int 				| FK			| User-->id		|
|createdOn 		| date 				|				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				| 				|



### District
|District		| type 				| remark 		| description	|
|	-			|-					|-				| -				|
|id				| int				| PK			|				|
|name			| varchar(40)		| 				|				|
|state			| int 				| FK			| State-->id	|
|createdBy 		| int 				| FK			| User-->id		|
|createdOn 		| date 				|				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				| 				|



### State
|State			| type 				| remark 		| description	|
|	-			|-					|-				| -				|
|id				| int				| PK			|				|
|name			| varchar(25)		| 				|				|
|createdBy 		| int 				| FK			| User-->id		|
|createdOn 		| date 				|				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				| 				|



### VillageAuthority
|VillageAuthority	| type 				| remark 		| description		|
|	-				| -					| - 			|- 					|
|id 				| int				| PK			|					|
|villageID			| int				| FK			| Village-->id		|
|authorityID		| int				| FK			| Authority-->id	|
|validFrom			| date 				|				|					|
|validTill			| date 				|				|					|
|createdBy 			| int 				| FK			| User-->id			|
|createdOn 			| date 				|				|					|
|editedBy 			| int 				| FK			| User-->id			|
|editedOn 			| date 				|				|					|



### AuthorityType
|AuthorityType 	| type 				| remark 		| description	|
|	-			| -					| - 			| -				|
|id 			| int				| PK			|				|
|name			| varchar(50)		| 				|				|
|status 		| enum ['0','1'] 	| as select '1'	|				|
|createdBy 		| int 				| FK			| User-->id		|
|createdOn 		| date 				| 				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				|				|


### Block
|Block	 		| type 				| remark 		| description		|
|---			|---				|---			|---				|
|id				| int 				| PK 			|					|
|name			| varchar(50)		|				|					|
|village		| int				| FK			| Village-->id		|
|tpsId			| int				| FK			| Tps-->id 			|
|area			| float				| 				|					|
|jantriRate		| float				|				|					|
|plotCategory 	| int				|				| PlotCategory-->id	|
|createdBy 		| int 				| FK			| User-->id			|
|createdOn 		| date 				| 				|					|
|editedBy 		| int 				| FK			| User-->id			|
|editedOn 		| date 				|				|					|

### BlockOwner
|BlockOwner 	| type 				| remark 		| description			|
|	-			|-					|- 				| -						|
|id				| int 				| PK 			|						|
|blockId 		| int				| FK			| Block-->id			|
|name			| varchar			|				|						|
|ownershipType	| int				| FK			| OwnershipType-->id	|
|address		| longtext			| 				|						|


### OwnershipType
|OwnershipType	| type 				| remark 		| description	| 
|	-			|-					|-				| -				|
|id				| int 				| PK			|				|
|name			| varchar			|				|				|
|status 		| enum ['0','1'] 	| as select '1'	|				|
|createdBy 		| int 				| FK			| User-->id		|
|createdOn 		| date 				|				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				|				|


### Case
|Case			| type 				| remark 		| description	|
|	-			|-					|-				| -				|
|id				| int 				| PK			|  				|
|caseNo			| int				|				|				|
|tpsId			| int				| FK			| Tps-->id		|
|createdBy 		| int 				| FK			| User-->id		|
|createdOn 		| date 				|				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				|				|


### OP
|OP				| type 				| remark		| description	|
|	-			|-					|-				| - 			|
|id				| int 				| PK 			| 				|
|caseId 		| int				| FK			| Case-->id		|
|caseSequenceId | int				|				| 				|
|createdBy 		| int 				| FK			| User-->id		|
|createdOn 		| date 				|				|				|
|editedBy 		| int 				| FK			| User-->id		|
|editedOn 		| date 				|				|				|


### OpRecord
|OpRecord		| type 				| remark		| description	|
|	-			|-					|-				| -				|
|id				| int 				| PK			| 				|
|opId 			| int				| FK			| OP-->id		|
|blockId 		| int				| FK			| Block-->id	|
|blockAreaUsed	| float 			| 				|				|
|blockValue 	| float 			|				|				|
|valueWOConst	| float				| 				|				|
|valueOfConst 	| float 			|				|				|
|valueWConst	| float 			|				|				|

### FP
|FP 				| type 				| remark		| description
|	-			|-					|-				| -
id 				| int 				| PK			|
fpId 			| int				|				|
caseId 			| int				| FK			| Case-->id
createdBy 		| int 				| FK			| User-->id
createdOn 		| date 				|				|
editedBy 		| int 				| FK			| User-->id
editedOn 		| date 				|				|


### FpRecord
|FpRecord 			| type 				| remark 	| description
|	-				|-					|-			| -
id 					| int				| PK		|
fpId 				| int				| FK		| FP-->id
opId 				| int				| FK		| OP-->id
opAreaUsed 			| float 			| 			|
opValue 			| float 			|			|
valueWOConst		| float				| 			|
valueOfConst 		| float 			|			|
valueWConst			| float 			|			|
roadFactor			| int				| FK		| Road-->roadFactor
cornerFactor	 	| int				| FK		|
reservationFactor	| int 				| FK		|
generalFactor		| int				| FK		|
finalValue			| float 			|			|
vuawoconstruct		| float 			|			|
vuawconstruct		| float				|			|



### RoadWidth
|RoadWidth 			| type 				| remark 		| description
|	-				|-					|-				| -
id 					| int				| PK			|
roadWidth			| varchar(3)		|				|
tpId				| int				|				| Tps-->id
status 				| enum ['0','1'] 	| as select '1'	|
createdBy 			| int 				| FK			| User-->id
createdOn 			| date 				|				|
editedBy 			| int 				| FK			| User-->id
editedOn 			| date 				|				|


### Road
|Road 				| type 				| remark				| description
|	-				|-					|- 						|-
id					| int				| PK					| 
roadLength 			| float(10)			|						|
roadWidthId			| int 				| 						| RoadWidth-->id
lane				| varchar(3)		|						|
carpetWidth			| varchar(5)		|						|
rate				| float(10)			|						|
cost				| float(20)			| = roadLength X rate	| 
roadFactor 			| float				|						|
createdBy 			| int 				| FK					| User-->id
createdOn 			| date 				|						|
editedBy 			| int 				| FK					| User-->id
editedOn 			| date 				|						| 


### StreeLight
|streetLight			| type 				| remark						| description
|	-				|-					|-								| -
id					| int				| PK							|
roadWidthId			| int 				| FK							| RoadWidth-->id
poleDistance		| varchar(3)		|								|
totalPole			| varchar(5)		|= poleDistance X roadLength	| 
rate				| float(10)			|								|
cost				| float(20)			|= totalPole X rate				|
createdBy 			| int 				| FK							| User-->id
createdOn 			| date 				|								|
editedBy 			| int 				| FK							| User-->id
editedOn 			| date 				|								|


### Drainage
|Drainage			| type 				| remark				| desctiption
|	-				|-					|-						| -
id					| int				| PK					|
roadWidthId			| int				| FK					| RoadWidth-->id
pipeSize			| varcahr(7)		|						|
rate				| float				|						|
cost				| float				|= roadLength X rate	|
createdBy 			| int 				| FK					| User-->id
createdOn 			| date 				|						| 
editedBy 			| int 				| FK					| User-->id
editedOn 			| date 				|						|



### WaterLine
|WaterLine			| type 				| remark								| description
|	-				|-					|-										| -
id					| int				| PK									|
roadWidthId			| int				| FK									| RoadWidth-->id
pipeSize			| varcahr(7)		|										|
wastagePer	 		| float				|										|
wastage 			| float				| = roadLength +(pipeSize X wastagePer)	|
rate				| float				|										|
cost				| float				|= roadLength X rate					|
createdBy 			| int 				| FK									| User-->id
createdOn 			| date 				|										|
editedBy 			| int 				| FK									| User-->id
editedOn 			| date 				|										|



### StormWaterDrainage
|StormWaterDrainage	| type 				| remark				| description
|	-				|-					|-						| -
id					| int				| PK					|
roadWidthId			| int				| FK					| RoadWidth-->id
pipeSize			| varcahr(7)		|						
rate				| float				|						|
cost				| float				|= roadLength X rate	|
createdBy 			| int 				| FK					| User-->id
createdOn 			| date 				|						|
editedBy 			| int 				| FK					| User-->id
editedOn 			| date 				|						|


### TpSetting
|TPSetting	 		| type 				| remark	| description
|	-				|-					|-			| -
id 					| int 				|			|
work				| varchar			|			|
contingencyWork		| float				|			|
priceIncrement1yr	| float				|			|
priceIncrement2yr	| float				|			|
areaDevelopmentCost	| float				|			|


### CornerFactor
|CornerFactor		| type 				| remark		| description
|	-				| -					| -				| -
id 					| int				| PK			|
road1				| int 				| FK			| RoadWidth-->id
road2				| int				| FK			| RoadWidth-->id
cornerFactor		| float				| 				|
status 				| enum ['0','1'] 	| as select '1'	|
createdBy 			| int 				| FK			| User-->id
createdOn 			| date 				|				|
editedBy 			| int 				| FK			| User-->id
editedOn 			| date 				|				|


### ReservationFactor
|ReservationFactor 	| type 				| remark		| description
|	-				| -					| -				| -
id					| int 				| PK			|
reservation			| varchar(50)		|				|
reservationFactor	| float				|				|
status 				| enum ['0','1'] 	| as select '1'	|
createdBy 			| int 				| FK			| User-->id
createdOn 			| date 				|				|
editedBy 			| int 				| FK			| User-->id
editedOn 			| date 				|				|

### GeneralFactor
|GeneralFactor	 	| type 				| remark		| description
|	-				| -					| -				| -
id					| int 				| PK			|
general				| varchar(50)		|				|
generalFactor		| float				|				|
status 				| enum ['0','1'] 	| as select '1' |
createdBy 			| int 				| FK			| User-->id
createdOn 			| date 				|				| 
editedBy 			| int 				| FK			| User-->id
editedOn 			| date 				|				| 


### PlotCategory
|PlotCategory	 	| type 				| remark		| description
|	-				| -					| -				| -
id					| int 				| PK			| 
name 				| varchar(40)		| 				|
tpId				| int 				| FK			| Tps-->id
status 				| enum ['0','1'] 	| as select '1' |
createdBy 			| int 				| FK			| User-->id
createdOn 			| date 				|				| 
editedBy 			| int 				| FK			| User-->id
editedOn 			| date 				|				| 

