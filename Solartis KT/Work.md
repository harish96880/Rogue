#change_version
	
	The tasks are assigned by ramalakshmi to us. Those are like creating api's, debugging api's etc. After that we given by developer access for the repository we're going to work which is given in the gitlab. Once we've create the api, we've to push that files into platform kb which contains the id of 6383. Here is the sample query for inserting files.

```sql
INSERT INTO CNF_KNOWLEDGE_BASE_DETAIL  
(CNF_KNOWLEDGE_BASE_DETAIL_ID, OWNER_ID, CNF_KNOWLEDGE_BASE_ID, CNF_PLATFORM_RELEASE_ID, RULEFILE_NAME,  
RULEFILE_PURPOSE, RULEFILE_TYPE, RULEFILE_LOCATION, START_DATE, END_DATE, RULEFILE_CREATED_BY, ACTIVE, CREATED_BY, CREATED_DATE,   
UPDATED_BY, UPDATED_DATE, CHANGE_VERSION, KB_LOAD_SEQUENCE, `GENERATED`,`MODE_NUMBER`) VALUES  
(947497824, 1, 6386, 1, 'GetSublineList_1.0.1.bpmn', 'To get list of sublines by state', 'bpmn',   
'/knowledgebase/com/solartis/event/Solartis/WorkflowV1/Common/Workflow/GetSublineList_1.0.1.bpmn',  
NOW() - INTERVAL 1 DAY, NOW() + INTERVAL 100 YEAR, 'Platform_Rakesh', 'Y', 'Platform_Rakesh', NOW(), 'Platform_Rakesh',   
NOW(), NULL, NULL, 'NO',1);
```

	After that we've to prepare a request json and response json and send those to business analyst. With the given details they are able to create an event for our api in builder. After the creation of event, we must ensure that our processId of main bpmn is linked in cnf_knowledge_base table. After that we have to test the api once ensure that there are no bugs we have to rebuild the multikb node and publish the change version to our uci pipeline.

### PlatformExtendedSupport Class

```java
PlatformExtendedSupport platformExtendedSupport=new PlatformExtendedSupport();
platformExtendedSupport.setErrorMessageInformation(requestDetailMap);
platformExtendedSupport.initializePerformanceList(requestDetailMap);
platformExtendedSupport.updatePerformanceList(requestDetailMap);
platformExtendedSupport.handleCatchBlockExceptionKeys(requestDetailMap,exception);
```
This SQL query retrieves data from four tables: `CNF_OBJECT_SCRIPTS`, `CNF_GET_DATA_SCRIPTS_ASSTN` , `CNF_GET_DATA_CHILD`, and `CNF_GET_DATA_MASTER` . It links these tables using join operations based on their respective IDs (`CNF_OBJECT_SCRIPTS_ID`, `CNF_GET_DATA_CHILD_ID`, and `CNF_GET_DATA_MASTER_ID`). The query filters the results to only include rows where `m.NAME` equals "${master_name}$" and `c.NAME` equals ''. This structured approach ensures that data related to script objects, data associations, child data, and master data is retrieved specifically for entries related to validation of request key information within the specified context.