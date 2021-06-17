
**INFORMATION:** 

The architecture and policy files used in the Section 7 of paper can be found in <b>"(Blind) For Peer Review - Policy and Arch files with screenshot.zip"</b>.  

The tool used in the verification of the files is <b>DataProVe-v0.9.8-blind.pyc </b>.   
- It requires Python 3.8 or newer to run correctly. 
- To run it, just double click on the file (Windows OS) or use the command <b>python DataProVe-v0.9.8-blind.pyc </b> (in Linux)
- The User Manual contains detailed user manual and a wide range of examples (including GUI-based examples and Text Mode examples).

VERSION INFO: 
- <b>Version 0.9.8 uploaded (June 8, 2021)</b>:
    - The tool supports any number of layers of nested cryptographic functions/encryption inside a datatype.
    - Added three attacker models: External attackers, insider attackers, hybrid attackers. The user can verify if an architecture comforms with a policy in the presence of 1)             external attackers, 2) insider attackers, and 3) hybrid (colluding external and insider) attackers. The three new verification options can be found under the tab "VERIFY".
    - In the policy specification page, the entity called "att" is added to the list of default entities (besides sp), to model the attacker(s).
    - Improved verification speed.
    - The file "v0.9.8-Pol and arch files in the manual.zip" contains the template files for the nested crypto, and attackers (in the folder "Examples-TEXTMODE").
    - To specify that the insider attackers have compromised the entities E1,...,En, in the menutab "SPECIFY THE RELATION BETWEEN THE MAIN COMPONENTS AND THE SUB-COMPONENTS", provide      att:E1,...,En.

**FEATURES SUPPORTED:**

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/features.png)

**EXAMPLE VERIFICATION IN THE BENIGN ENVIRONMENT (NO ATTACKERS):** 

We define an example policy that we will use for our next examples. In the policy, we define three data types, specifically: 1) name, 2) address, and 3) job (which we defined as UNIQUE, just for checking the unique linkability of name and address).

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/pol1.png)

We select the default/pre-defined entity att (attacker) to specify its data possession and linkability sub-policies. Obviously, we do not allow the attacker to have name and address, and to link them “uniquely”. 

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/pol2.png)

The same data possession sub-policy is defined for address and job.

And for linkability, we have: 

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/pol3.png)

Besides the following architecture, the service provider (sp) can have and link name with address. 

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/benign.png)

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/benignbutton.png)

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/benignverif.png)

**EXAMPLE VERIFICATION IN THE PRESENCE OF ATTACKERS:** 

EXTERNAL ATTACKER CASE:

Besides the following architecture, the external attackers who can eavesdrop the data during transmission can have and link name with address. 

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/exatt.png)

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/exattbutton.png)

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/exattverif.png)

INSIDER ATTACKER CASE:

Besides the following architecture, the insider attackers who can compromise benign entities can have and link name with address. 

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/inatt.png)

We set that the insider attacker(s) has access to/has full control over the benign entities to model that those entities have been compromised.  

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/inattrel.png)

As a result we get: 

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/inattverif.png)

HYBRID ATTACKER CASE:

Besides the following architecture, we check what happens if the insider attacker(s) shares data with the external attacker(s) :

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/hybatt.png)

We set that the hybrid attacker(s) has access to/has full control over the benign entities to model that those entities have been compromised.  
Unlike the insider attackers case above, the service provider has not been compromised (att cannot control fully sp).

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/hybattrel.png)

However, by colluding with the external attacker(s), the data captured during transmission can be used. 

As a result we get: 

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/hybattverif.png)

**VIDEOS (blind):** 
- Video about the GUI examples : https://youtu.be/0UlmTfseTUw
- Video about the Textmode examples: https://youtu.be/uBKVCnsok-c
- Video about verifying the two contact tracing approaches: https://youtu.be/IAiSS2Ol8OI

**CODE EXCERPT:**
- Part of the unification procedure (where MAPRECORD keeps track of the mapping resulted from unification steps): 
    
    ![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Code%20excerpt/Code-part%20of%20unify.png?raw=true)
    
- Part of the cryptographic unification: 

    ![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Code%20excerpt/Code-Crypto-part.png?raw=true)
    
- Part of the verification against architecture actions: 

     ![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Code%20excerpt/Code-checkagainstArch.png?raw=true)

- Part of the verification (proof tree) process: 

    ![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Code%20excerpt/Code-Verif-part.png?raw=true)
   
- Part of ruleset: 

    ![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Code%20excerpt/Code-ruleset.png?raw=true)

