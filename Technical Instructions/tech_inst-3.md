## Test 12049
Submit one document via XDS.b

Verify that the XDS.b Document Source can submit a single document via Provide and Register Document Set-b transaction. 

**References:** ITI TF-2 3.41

**Actor:** Document Source

**Dependencies:** None

**Resources:** NIST XDS ToolKit

**Test Procedure**  

a. Access NIST XDS Toolkit  

b. Select a proper test session and the default environment codes  

c. Go to the “Simulators” menu option. Configure a new Registry and new Repository simulators. Open the Repository configuration and inform the Registry endpoint  

d. Go to the “Manage Patient IDs” menu option. Select one patient ID, select your register simulator and click on “Run” bottom to send a patient feed transaction to your register simulator  

e. Use your SUT (document source) to submit a Submission Set containing a single Document using the Provide and Register Document Set-b transaction  

f. Go to the “Simulators” menu option. Select your repository simulator, click on the “log” action  
![](./media/image3-1.png)

g. Select the “message” you have just generated. Take a screenshot of this screeen and click on the “Download message” option.

![](./media/image3-2.png)  
h. Post the generated zip file and screenshot to Gazelle Action “return log file”.  


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

a Use same patient ID used for Test 12049.  

b. Use your SUT (document consumer) to submit a “FindDocument” Stored Query retrieving all documents for this patient ID.  

c. Go to the “Simulators” menu option. Select your registry simulator, click on the “log” action (similar to step 6 of test 12049).  

d. Select the “message” you have just generated. Take a screenshot of this screeen and click on the “Download message” option (similar to step 7 of test 12049).  

e. Post the generated zip file and screenshot to Gazelle Action “return log file”.  

