# Dataprovetool

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
    - Added more TEXTMODE examples in the "Pol and Arch files used in the manual" (including the example with CALCULATEFROMAT)
    - Improved the user manual, make it more related to the version 0.9.6.
