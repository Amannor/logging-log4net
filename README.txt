****************************************************************************************************************************************
Explanation on this fork
========================
This branch contains the fix of the serialization bug described here: https://issues.apache.org/jira/browse/LOG4NET-398
This is a fork from the log4net project, release 1.2.13 (RC-3), which is marked in the original project by the git tag "rc/1.2.13-RC3". Hence, if you wish to see the code changes I've made, make sure to diff this branch from the branch of the original project *at the tag rc/1.2.13-RC3*.
The reason I fixed it in this old version is because that's the legacy code that I got in the project I was assigned :)

- The bug, in a nutshell, is a serializationException that occurred due to an assignment of value to log4net.logicalthreadcontext. The reason is that the same object that log4net are using can't switch successfully between AppDomains. 
- The solution is to have that object inherit from MarshalByRefObject

To compile this code (on a Windows computer)
============================================
1) Download the compilation mechanism called nant. It can be downloaded from this link (the version I used is 0.92 but it doesn't really matter). If for some reason the file can't be downloaded, I've added it to this branch under the folder "_AuxiliaryFolderNotPartOfOriginalProject".
Download link: http://nant.sourceforge.net/

2) Right click on the downloaded zip file, choose "Properties" -> "General" -> Check the box tha reads "Unblock".

3) Extract the downloaded zip file to c:\Program Files\NAnt

4) Look for the file "build.cmd" in this project and make sure it has the correct fullpath of the nant.exe file.

5) Open a cmd window As Administrator

6) Goto the homefolder of where you downloaded this project.

7) Run "build.cmd compile-all"

8) The compiled artifacts are in the project folder under "...\bin\net\..."
****************************************************************************************************************************************

* Hereinafter is the original README text *

Project Status
==============

Apache log4net is a sub project of the Apache Logging Services project. 
Apache log4net graduated from the Apache Incubator in February 2007.
Web site: http://logging.apache.org/log4net


Documentation
=============

For local documentation, which is correct for this release see:
doc/index.html

For the latest documentation see the log4net web site at:
http://logging.apache.org/log4net
