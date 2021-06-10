**CONCEPT/VISION OF THE FRAMEWORK:**

The picture below depicts the rationale and concept behind the DataProVe framework, which also somewhat indicates the decision on the choice of languages variants and verification engine.

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/DataProVe-framework.png?raw=true)


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
    - The file "Pol and arch files used in the manual v0.9.8.zip" contains the template files for the nested crypto, and attackers (in the folder "Examples-TEXTMODE").
    - To specify that the insider attackers have compromised the entities E1,...,En, in the menutab "SPECIFY THE RELATION BETWEEN THE MAIN COMPONENTS AND THE SUB-COMPONENTS", provide      att:E1,...,En.

**FEATURES SUPPORTED:**

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

