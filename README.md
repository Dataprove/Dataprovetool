
**INTRODUCTION:**

With DataProVe, users can specify a high-level data protection (or privacy) policy and a system architecture, then verify the conformance between the specified architecture and the high-level policy.  

The main goal of DataProVe is to help system designers at the higher level (compared to other tools that mainly focus on the protocol/implementation or code levels.), such as with the policy and architecture design. This step can be important to spot high-level design flaws early, before going ahead with the lower level system specification. 

DataProVe may be useful for education purposes as well, especially, where the subject is about personal data protection or privacy.  

The research on DataProVe is led by Dr. Vinh Thong Ta (at Edge Hill University, UK, contact: tav at edgehill dot ac dot uk). 

The verification engine of DataProVe is based on logic ("guided" resolution based proofs), combining both the so-called backward and forward search strategies.

DataProVe comes with GUI (graphical user interface), and the current version is written in Python. 

- The source code and full user manual can be found in the folder Artifacts: 
    - Source code (.py): https://github.com/Dataprove/Dataprovetool/blob/main/Artifacts/DataProVe-prototype.py
    - User manual (.pdf):  https://github.com/Dataprove/Dataprovetool/blob/main/Artifacts/DataProVe%20Manual%20nov%202021.pdf
    - Template files (.zip): https://github.com/Dataprove/Dataprovetool/blob/main/Artifacts/Pol%20and%20arch%20files%20used%20in%20the%20manual%20v0.9.8.zip


**HOW TO RUN:** 
- DataProVe requires Python 3.8 or newer to run correctly. 
- To run it, just double click on the file (Windows OS) or use the command 
  - <b>python DataProVe-vx.y.z.pyc </b> (where vx.y.z represents the current version number) for the pyc file, or
  - <b>python DataProVe-prototype.py </b> for running directly from the source file. 
- The user manual contains detailed user manual and a wide range of examples (including GUI-based examples and Text Mode examples).

**SUPPORTED OPERATING SYSTEMS:** 
- DataProVe was implemented and only tested on Windows 7/10. The current version of the tool has not been tested on macOS or Linux yet. 

**SOFTWARE DEPENDENCIES:**
The tool requires
- Python 3.8 or higher
- The tkinter package (python-tk) that supports GUI features. 
- Further packages required: time, webbrowser, json, itertools, re.

**FEATURES AND OPTIONS SELECTIONS**

After launching the tool, the first thing the user will see is a frame with a (light) red area. This is the architecture specification page, where the user can either "draw" a graphical architecture by adding the main and sub-components and lines that connect the components or launch a text editor.

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard01.png" width=70% height=70%>

In this frame, the options and features of the tool can be found in the menu bar (at the top left corner). The options are organised under the following tabs: 
1. Policy specification options
2. Options for specifying architectures in GUI mode. 
3. Options for specifying architectures in textual mode.  
4. Options for conformance verification. 

**USER INPUTS (INTERACTION WITH THE TOOL)**
1. **Policy**: The users can input their policy related parameters and settings directly in GUI policy specification page (blue frame). 
2. **Architecture GUI mode**: The user can specify their graphical architectures using the options add component in the menu bar. The architecture actions can be given in the textboxes. 
3. **Architecture textual mode**: Using the launch text editor option in the menu bar, the user opens a textbox where they can input each architecture action line by line. The content of this textbox area can be freely modified. 



**A WALKTHROUGH EXAMPLE**

The policy and architecture files related to this example can be found in the folder https://github.com/Dataprove/Dataprovetool/tree/main/Walkthrough%20example%20files.

This section provides a simple example to help the user understand how to use the tool step by step. The example is based on a simple smart metering system, where the service provider (sp) collects gas and electric readings, and calculate the bill based on those.

**Step 1:** After launching the tool, the user will see the architecture specification page (a red colour frame).  

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard02.png" width=70% height=70%>

**Step 2:** Choosing the option “Specify a New Data Protection Policy”, the users will see a blue frame where they can specify their policy from scratch. 

**Step 3 (Entities):** By default, there are two (built-in) entities, the service provider (sp), and the attacker (att). Let’s add two more entities for the smart metering service: the meter (meter) the customer (cust), and the third party (third).    

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard04.png" width=70% height=70%>

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard03.png" width=70% height=70%>

**Step 4 (Data types):** The next step is to define the data types supported by the service. For simplicity, we define two data types: 
1. Personal information (personal) that represents name, address, email, and phone number.   
2. Energy reading (energy) that covers gas, electric. 

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard05.png" width=70% height=70%>

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard06.png" width=70% height=70%>

**Step 5 (Sub-policies):** Now, we can start our sub-policy specifications for each data type.  
1.	For the data type personal (choose personal in the tab above, then click on “Data Collection”): 
    1.	the collection sub-policy is (Y, {create:account}), which means that consent is required for collecting this type of data and the purpose of collection is to create an account.<br/><br/>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard07.png" width=65% height=65%><br/>
    
    2. The usage sub-policy is (Y,{create:billdoc}), which means that consent is required to use personal info, with the purpose of creating a bill document. <br/><br/>


    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard08.png" width=65% height=65%><br/>

    3. The storage sub-policy is (Y,{mainstorage}), which means that the consent is required for data storage. In addition, the data is stored in the main storage place(s) of the service provider. <br/><br/>

     <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard09.png" width=65% height=65%><br/>

    4. The retention sub-policy is ({mainstorage},2y), which means that this type of data is only kept in the main storage at most for 2 years. <br/><br/>
    
     <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard10.png" width=65% height=65%><br/>

    5.  For the data transfer policy, we do not allow personal and energy to be forwarded. Hence, the transfer sub-policy is empty. 
    6.  The has sub-policy is {sp, meter, cust}, which means that only sp, meter and cust have the right to access this type of data. This also means that third and att do not have the right to access this type of data.  <br/><br/>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard11.png" width=65% height=65%>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard12.png" width=65% height=65%>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard13.png" width=65% height=65%><br/>
    
    7. The link sub-policy (permit) is {(sp, energy), (cust, energy)}, which means that only sp and cust have the right to link personal with energy (i.e., they know the energy consumption for a given person/address).  <br/><br/>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard14.png" width=65% height=65%>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard15.png" width=65% height=65%><br/>
    
    8. The link sub-policy (forbid) is {(third, energy), (att, energy)}, which means that the third party and the attackers do not have the right to link personal with energy.  <br/><br/>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard16.png" width=65% height=65%>
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard17.png" width=65% height=65%><br/>
    
    9. For the data type energy, we define the similar sub-policies like the previous data type, with one exception. Specifically, in the data collection and usage sub-policies, energy is collected and used for the purpose of calculating the bill amount ({calculate:billamount}).  <br/><br/>
  
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard19.png" width=65% height=65%><br/>
    
    10. **Save the policy**: Under “POLICY” => “SAVE the Policy”, the user can save the policy for running a verification, reviewing, and modifying it later. 

**Step 6 (Architecture specification):** Once we finished with the policy specification, we can design and specify the architecture. 

We can specify our architecture for the smart metering service either in GUI or Text mode. Let’s start with the Text mode. 

TEXTUAL MODE: Under the ARCHITECTURE-TEXTMODE tab, we launch the text editor, and start adding the actions line by line. 
- RECEIVEAT(sp,energy,Time(t1))
- RECEIVEAT(sp,personal,Time(t2))
- RECEIVEAT(sp,CConsent(energy,sp),Time(t1))
- RECEIVEAT(sp,CConsent(personal,sp),Time(t2))
- RECEIVEAT(sp,UConsent(energy,sp),Time(t1))
- RECEIVEAT(sp,UConsent(personal,sp),Time(t2))
- RECEIVEAT(sp,SConsent(energy,mainstorage),Time(t3))
- RECEIVEAT(sp,SConsent(personal,mainstorage),Time(t4))
- STOREAT(mainstorage,energy,Time(t3))
- STOREAT(mainstorage,personal,Time(t4))
- DELETEWITHIN(mainstorage,energy,Time(2y))
- DELETEWITHIN(mainstorage,personal,Time(2y))
- CREATEAT(sp,Account(personal),Time(t2))
- CREATEAT(sp,BillDoc(personal,energy,BillAmount(energy)),Time(t1))
- CALCULATEAT(sp,BillAmount(energy),Time(t1))
- CALCULATEAT(meter,energy,Time(t8))
- OWN(cust,personal)
- RECEIVEAT(cust,BillDoc(personal,energy,BillAmount(energy)),Time(t9))<br/><br/>

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard18.png" width=65% height=65%><br/>

Click “SAVE CONTENT”. The architecture in text mode needs to save before conformance verification. 

The next step is to set the relationship between the entities sp and meter, and cust and meter. Under the tab “ARCHITECTURE-TEXTMODE”, we choose “SPECIFY THE RELATIONSHIP BETWEEN THE MAIN AND SUB-COMPONENTS (TEXT)”, which opens a window where we can provide two lines: sp:meter and cust:meter. This means that sp and cust have access to the reading of meter.<br/>

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard17b.png" width=65% height=65%><br/>

Save the architecture: Under “ARCHITECTURE-TEXTMODE” => “SAVE the Architecture (Text)”, the user can save the architecture for running a verification, reviewing, and modifying it later. 

**Step 7 (Conformance verification):**     

Once we are ready with the policy and architecture specifications, we can run the conformance verification. We can choose among four options. 
1. Run the verification without the presence of any attacker (e.g., the entity att is ignored).  

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard21.png" width=65% height=65%><br/>

2. Run the verification to check if the has and link sub-policies are violated assuming the external attacker(s).<br/><br/>

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard22.png" width=65% height=65%><br/>

Since the messages exchanged are unencrypted, the external attacker who eavesdrop on the communication can obtain personal, energy and link personal to energy due to the bill document (BillDoc). 

3. Run the verification to check if the has and link sub-policies are violated assuming (only) the insider attacker(s).

    To verify against insider attackers, we need to define which entity/component has been compromised by the attacker (that has full access to the compromised entity). For example, we specify that the attacker has access to meter. 

    Under “SPECIFY THE RELATIONSHIP BETWEEN THE MAIN AND SUB-COMPONENTS (TEXT)”, we add: att:meter.  

    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard23.png" width=65% height=65%><br/>

    As the verification result, we get that the insider attacker only have access to energy (because of the compromised meter), but not to personal. 
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard24.png" width=65% height=65%><br/>

4. Run the verification to check if the has and link sub-policies are violated assuming the hybrid attacker(s).
  
    The hybrid attacker case is the combination of the external and insider attackers.

    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard25.png" width=65% height=65%><br/>


**Step 8 (Optional):** 

We can make changes to our architecture so that it is secured against external attackers, by applying encryption on the exchanged messages. To do this, we change the actions (directly in the text editor) to, for example:

- RECEIVEAT(sp,Senc(energy,key),Time(t1))
- RECEIVEAT(sp,Senc(personal,key),Time(t2))
- RECEIVEAT(cust,Senc(BillDoc(personal,energy,BillAmount(energy)),key),Time(t9))
- RECEIVEAT(sp,CConsent(energy,sp),Time(t1))
- RECEIVEAT(sp,CConsent(personal,sp),Time(t2))
- RECEIVEAT(sp,UConsent(energy,sp),Time(t1))
- RECEIVEAT(sp,UConsent(personal,sp),Time(t2))
- RECEIVEAT(sp,SConsent(energy,mainstorage),Time(t3))
- RECEIVEAT(sp,SConsent(personal,mainstorage),Time(t4))
- STOREAT(mainstorage,energy,Time(t3))
- STOREAT(mainstorage,personal,Time(t4))
- DELETEWITHIN(mainstorage,energy,Time(2y))
- DELETEWITHIN(mainstorage,personal,Time(2y))
- CREATEAT(sp,Account(personal),Time(t2))
- CREATEAT(sp,BillDoc(personal,energy,BillAmount(energy)),Time(t1))
- CALCULATEAT(sp,BillAmount(energy),Time(t1))
- CALCULATEAT(meter,energy,Time(t8))
- OWN(cust,personal)
- OWN(cust,key)
- OWN(sp,key)

After clicking “SAVE CONTENT”, we can run the verification against external attackers to see the difference in the result. 

<img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard26.png" width=65% height=65%><br/>

**ADDITIONAL APPLICATION EXAMPLES:**
- More examples can be found in the user manual, starting from page 39 (https://github.com/Dataprove/Dataprovetool/blob/main/Artifacts/DataProVe%20Manual%20nov%202021.pdf). 
- Each example presents the settings and specification guideline for different sub-policies. We also provide examples for architectures with cryptographic primitives, and verification against different attacker types. 
- The template files for those examples can be found in the "Pol and arch files used in the manual v.0.9.8.zip" file (https://github.com/Dataprove/Dataprovetool/blob/main/Artifacts/Pol%20and%20arch%20files%20used%20in%20the%20manual%20v0.9.8.zip).  

**DEMO VIDEOS:** 
- Video about the GUI examples : https://youtu.be/0UlmTfseTUw
- Video about the Textmode examples: https://youtu.be/uBKVCnsok-c
- Video about verifying the two contact tracing approaches: https://youtu.be/IAiSS2Ol8OI



