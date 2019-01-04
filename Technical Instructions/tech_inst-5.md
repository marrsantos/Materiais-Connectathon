### Test PIXv3_FEED

The Patient Identity Source actor must demonstrate 3 capabilities:

- admit/register a patient with PRPA_IN201301UV02: Patient Registry Record Added
- update a patient with PRPA_IN201302UV02: Patient Registry Record Revised
- merge with PRPA_IN201304UV02: Patient Registry Duplicates Resolved

The Patient Identity Source needs to have an Assigning Authority assigned to its own system for identifying that source. The IHE Technical Manager will provide an OID to be used as the Assigning Authority for your system. 

> Request the IHE Technical Manager the OID for your company and only perform this test using this OID.

**References:** ITI TF-2b 3.44 Patient Identity Feed HL7 V3 [ITI-44]

**Actor:** Patient Identity Source

**Dependencies:** None

**Resources:** [Gazelle Patient Manager](https://gazelle.ihe.net/PatientManager/hl7v3/pix/xmanager.seam)

**Test procedure**

a) Access the Patient Manager tool: [http://gazelle.ihe.net/PatientManager](http://gazelle.ihe.net/PatientManager).

b) Go to menu PIX → Patient Identifier Cross-Reference Manager. Next, select HL7v3 Configuration.

c) The tool will display the configuration details you will need to query the PIX Manager Simulator. Ensure the status of the Simulator is "Running".

![](./media/image5-1.png)


d) Configure your System Under Test (SUT) to perform a Patient Registry Record Added transaction (PRPA_IN201301UV02) against the PIX Manager simulator endpoint.   
   - Create a new Patient named “Maria Auxiliadora Silva” (given=”Maria Auxiliadora” and family=”Silva”), gender “female”, address “Avenida Brasil, 300”/“Belo Horizonte” and Country “Brazil”.   
   - This new Patient will have a new id with the Assigning Authority OID provided by the IHE Technical Manager to your system. Take note of this Patient name and id.  
   - Verify ITI TF-2b Table 3.44.4.1.2.2-1 Model Attributes in order to represent these patient data. 
   - Pay attention to the ITI TF-2b Table 3.44.4.1.2.3-1: Wrappers and Constraints. 

e) Perform another Patient Registry Record Added transaction (PRPA_IN201301UV02) against the PIX Manager simulator endpoint.   
   - Create a new Patient named “Maria [Your Company first Name]” (given=”Maria” and family=”Your Company first Name”), gender “female”, address “Avenida Brasil, 300”/“Belo Horizonte” and Country “Brasil”.   
   - This new Patient will have a new id with the Assigning Authority OID provided by the IHE Technical Manager to your system. Take note of this Patient name and id.  

f) Perform a Patient Registry Record Revised transaction (PRPA_IN201302UV02) against the PIX Manager simulator endpoint.   
   - Update the previous patient “Maria [Your Company first Name]”. Last name stays the same [Your Company first Name] and first name will change from “Maria” to “Maria Auxiliadora”.   

g) Perform a Patient Registry Duplicates Resolved transaction (PRPA_IN201304UV02) against the PIX Manager simulator endpoint.   
   - Merge “Maria Auxiliadora Silva” into to last patient updated (Maria Auxiliadora [Your Company first Name]).   
   - Only Maria Auxiliadora [Your Company first Name] need to survive.  

h) You can use menu HL7 messages to find all ITI-44 requests & responses captured by the tool

![](./media/image5-2.png)

i) Take a screenshot of your application or your database as a proof of receipt of all ITI-44 responses. Retrieve the permanent link to the transaction instances, and paste that as evidence for this test. The screen shot demonstrates that you have successfully processed the processed all requests and response(s).

Note 1: You can use the menu “Messages Browser” to inspect and validate your messages. Click on the magnifying glass icon to inspect messages.

![](./media/image5-3.png)


When inspecting messages you will have the option to verify the validation results.


![](./media/image5-4.png)













