##Test 12049
Submit one document via XDS.b

Verify that the XDS.b Document Source can submit a single document via Provide and Register Document Set-b transaction. 

**References:** ITI TF-2 3.41

**Actor:** Document Source

**Dependencies:** None

**Resources:** NIST XDS ToolKit

**Test Procedure**  
1. Access NIST XDS Toolkit  
2. Select a proper test session and the default environment codes  
3. Go to the “Simulators” menu option. Configure a new Registry and new Repository simulators. Open the Repository configuration and inform the Registry endpoint  
4. Go to the “Manage Patient IDs” menu option. Select one patient ID, select your register simulator and click on “Run” bottom to send a patient feed transaction to your register simulator  
5. Use your SUT (document source) to submit a Submission Set containing a single Document using the Provide and Register Document Set-b transaction  
6. Go to the “Simulators” menu option. Select your repository simulator, click on the “log” action  
![](./media/image3-1.png)
7. Select the “message” you have just generated. Take a screenshot of this screeen and click on the “Download message” option.

![](./media/image3-2.png)  
8. Post the generated zip file and screenshot to Gazelle Action “return log file”.  


## Test 12046
Submit one document via XDS.b over TLS

Verify that the XDS.b Document Source can submit a single document via Provide and Register Document Set-b transaction over TLS. 

**References:** ITI TF-2 3.41

**Actor:** Document Source

**Resources:** NIST XDS ToolKit

**Test Procedure**

Repeat all steps of test 12049. However, perform Steps 3 and 5 over TLS.

## Tests 11936/12363
FindDocuments Stored Query and generic instructions for testing Document Consumer implementations of Stored Queries.

**References:** ITI TF-2 3.18

**Actor:** Document Consumer

**Resources:** NIST XDS ToolKit

**Test Procedure**  
1. Use same patient ID used for Test 12049  
2. Use your SUT (document consumer) to submit a “FindDocument” Stored Query retrieving all documents for this patient ID.  
3. Go to the “Simulators” menu option. Select your registry simulator, click on the “log” action (similar to step 6 of test 12049)  
4. Select the “message” you have just generated. Take a screenshot of this screeen and click on the “Download message” option (similar to step 7 of test 12049)  
5. Post the generated zip file and screenshot to Gazelle Action “return log file”.  

