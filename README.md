

In the DataProVe framework, users can specify a high-level data protection (or privacy) policy and a system architecture, then verify the conformance between the specified architecture and the high-level policy.  

The main goal of the framework is to help system designers at the higher level (compared to other tools that mainly focus on the protocol/implementation or code levels.), such as with the policy and architecture design. This step can be important to spot high-level design flaws early, before going ahead with the lower level system specification. 

DataProVe may be useful for education purposes as well, especially, where the subject is about personal data protection or privacy.  

The verification engine of DataProVe is based on logic ("guided" resolution based proofs), combining both the so-called backward and forward search strategies.

DataProVe comes with GUI (graphical user interface), and the current version is written in Python.  

The paper (long version) about the theoretical background of the tool can be read here: https://github.com/Dataprove/Dataprovetool/blob/main/Preprint%20-Blind.pdf.


**HOW TO RUN:** 
- DataProVe requires Python 3.8 or newer to run correctly. 
- To run it, just double click on the file (Windows OS) or use the command <b>python DataProVe-v0.9.8-blind.pyc </b> (in Linux and Mac OS)
- The user manual contains detailed user manual and a wide range of examples (including GUI-based examples and Text Mode examples).

**VERSION INFO:** 
- <b>Version 0.9.8-blind uploaded (June 8, 2021)</b>:
    - The tool supports any number of layers of nested cryptographic functions/encryption inside a datatype.
    - Added three attacker models: External attackers, insider attackers, hybrid attackers. The user can verify if an architecture comforms with a policy in the presence of 1)             external attackers, 2) insider attackers, and 3) hybrid (colluding external and insider) attackers. The three new verification options can be found under the tab "VERIFY".
    - In the policy specification page, the entity called "att" is added to the list of default entities (besides sp), to model the attacker(s).
    - Improved verification speed.
    - The file "PDP3T & PEP-PT files for v0.9.8-blind.zip" contains the template files for DP3T and PEP-PT.
    - To specify that the insider attackers have compromised the entities E1,...,En, in the menutab "SPECIFY THE RELATION BETWEEN THE MAIN COMPONENTS AND THE SUB-COMPONENTS", provide      att:E1,...,En.
    
**FEATURES SUPPORTED:**

![alt text](https://github.com/Dataprove/Dataprovetool/blob/main/Pictures%20for%20user%20manual/features.png)


**DEMO VIDEOS:** 
- Video about the GUI examples : https://youtu.be/0UlmTfseTUw
- Video about the Textmode examples: https://youtu.be/uBKVCnsok-c
- Video about verifying the two contact tracing approaches: https://youtu.be/IAiSS2Ol8OI



