**CONCEPT/VISION OF THE FRAMEWORK:**

The picture below depicts the rationale and concept behind the DataProVe framework, which also somewhat indicates the decision on the choice of languages variants and verification engine.

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/DataProVe-framework.png?raw=true)


**INFORMATION:** 

The architecture and policy files used in the Section 7 of paper can be found in <b>"(Blind) For Peer Review - Policy and Arch files with screenshot.zip"</b>.  

The tool used in the verification of the files is <b>DataProVe-v0.9.4-blind.pyc </b>.   
- It requires Python 3.8 or newer to run correctly. 
- To run it, just double click on the file (Windows OS) or use the command <b>python DataProVe-v0.9.4-blind.pyc </b> (in Linux)
- The User Manual contains detailed user manual and a wide range of examples (including GUI-based examples and Text Mode examples).

VERSION INFO: 
- v0.9.4: The earliest version that contains more details about the author. It is kept only for the record.
- v0.9.4-blind : Used for running the files for DP3T and PEP-IMP examples in the paper.
- v0.9.5-blind:  The same as v0.9.4-blind, but 
    - with improved message in the Data Possession Policy specification window (added the text "Y for Yes/Leave empty or N for No"), and 
    - Minor changes with the content of the warning messages in the verification results window. Namely, in "v0.9.4-blind", the warning messages for usage consent show "CALCULATE" for both the CALCULATE and CREATE actions (hence, seems redundant) due to copy paste error. This has been corrected and warning messages for the CALCULATE and CREATE actions can be found separately in the verification results window in "v0.9.5-bind". The example files can be run with this version as well.      
- v0.9.6-blind:
    - Actions CALCULATEFROM(component,Datatype1,Datatype2) and CALCULATEFROMAT(component,Datatype1,Datatype2,Time(t)) are added to specify a piece of data can be calculated from another piece of data.
    - Improved the notification text/presentation for the verification results.
    - The TEXTMODE saving also includes the list of relationships between main and sub-components, which will be then loaded in the program when the arch .txt file is opened.
    - Added more TEXTMODE examples in "Pol and Arch files used in the manual-v0.9.6.zip" inside DataProve-v0.9.6-all-in-one-blind.zip (including the example with CALCULATEFROMAT)
    - Improved the user manual, make it more related to the version 0.9.6 (can be found inside DataProve-v0.9.6-all-in-one-blind.zip).
    - DT3P and PEP-IMP specs. for v0.9.6 (can be found inside DataProve-v0.9.6-all-in-one-blind.zip). 


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

