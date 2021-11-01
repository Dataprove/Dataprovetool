
**INTRODUCTION:**

With DataProVe, users can specify a high-level data protection (or privacy) policy and a system architecture, then verify the conformance between the specified architecture and the high-level policy.  

The main goal of the framework is to help system designers at the higher level (compared to other tools that mainly focus on the protocol/implementation or code levels.), such as with the policy and architecture design. This step can be important to spot high-level design flaws early, before going ahead with the lower level system specification. 

DataProVe may be useful for education purposes as well, especially, where the subject is about personal data protection or privacy.  

The verification engine of DataProVe is based on logic ("guided" resolution based proofs), combining both the so-called backward and forward search strategies.

DataProVe comes with GUI (graphical user interface), and the current version is written in Python.  

The paper (long version) about the theoretical background of the tool can be read here: https://github.com/Dataprove/Dataprovetool/blob/main/Preprint%20-Blind.pdf.


**HOW TO RUN:** 
- DataProVe requires Python 3.8 or newer to run correctly. 
- To run it, just double click on the file (Windows OS) or use the command <b>python DataProVe-vx.y.z.pyc </b> 
- The user manual contains detailed user manual and a wide range of examples (including GUI-based examples and Text Mode examples).

**SUPPORTED OPERATING SYSTEMS:** 
- DataProVe was only thoroughly tested on Windows 7/10. This version of the tool has not been tested on macOS or Linux. 

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
    1.	the collection sub-policy is (Y, {create:account}), which means that consent is required for collecting this type of data and the purpose of collection is to create an account.
    
    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard07.png" width=65% height=65%>
    
    2. The usage sub-policy is (Y,{create:billdoc}), which means that consent is required to use personal info, with the purpose of creating a bill document. 


    <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard08.png" width=65% height=65%>

    3. The storage sub-policy is (Y,{mainstorage}), which means that the consent is required for data storage. In addition, the data is stored in the main storage place(s) of the service provider. 

     <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard09.png" width=65% height=65%>

    4. The retention sub-policy is ({mainstorage},2y), which means that this type of data is only kept in the main storage at most for 2 years. <br/>
    
     <img src="https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/Clipboard10.png" width=65% height=65%>

**DEMO VIDEOS:** 
- Video about the GUI examples : https://youtu.be/0UlmTfseTUw
- Video about the Textmode examples: https://youtu.be/uBKVCnsok-c
- Video about verifying the two contact tracing approaches: https://youtu.be/IAiSS2Ol8OI



