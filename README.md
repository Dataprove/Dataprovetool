
**INTRODUCTION:**

In the DataProVe framework, users can specify a high-level data protection (or privacy) policy and a system architecture, then verify the conformance between the specified architecture and the high-level policy.  

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

In this frame, the options and features of the tool can be found in the menu bar (at the top left corner). The options are organised under the following tabs: 
1. Policy specification options
2. Options for specifying architectures in GUI mode. 
3. Options for specifying architectures in textual mode.  
4. Options for conformance verification. 

**USER INPUTS (INTERACTION WITH THE TOOL)**
1. **Policy**: The users can input their policy related parameters and settings directly in GUI policy specification page (blue frame). 
2. **Architecture GUI mode**: The user can specify their graphical architectures using the options add component in the menu bar. The architecture actions can be given in the textboxes. 
3. **Architecture textual mode**: Using the launch text editor option in the menu bar, the user opens a textbox where they can input each architecture action line by line. The content of this textbox area can be freely modified. 






**DEMO VIDEOS:** 
- Video about the GUI examples : https://youtu.be/0UlmTfseTUw
- Video about the Textmode examples: https://youtu.be/uBKVCnsok-c
- Video about verifying the two contact tracing approaches: https://youtu.be/IAiSS2Ol8OI



