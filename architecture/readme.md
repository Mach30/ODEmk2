# System Architecture Documetation
This folder contains the system architecture description for Sliderule (the foundation for ODE Mk 2).  We will be modeling the architecture in SysML and implementing it using Agile methods (see the planning folder for materials concerning our Agile process).  The SysML model will be built in [Papyrus](https://www.eclipse.org/papyrus/).

# Architecture Folder Structure
The Architecture folder will contain the SysML model file(s).  We will store exports from the SysML model (and possibly other documentation) in separate folders, one for each [pillar of SysML](http://blog.ricksteiner.net/?p=127).

1. behavior - This folder contains descriptions of how the system should operate and how users should interact with it. User stories and CONOPS are two examples of content we will put in the behavior folder.
2. requirements - This folder contains formal requirements for the system.  Given our use of Agile methods, this folder may end up sparsely populated with preference going to the development of PBIs.
3. structure - This folder contains the structural description of the system.  Block diagrams, narative descriptions of the elements of the system, and information on how the Sliderule interacts with users and external resources are examples of conent we will put in the structure folder.  During architecture development, expect to see multiple possible implementations documented and discussed.
4. analysis - This folder contains documentation on how to verify and validate the system as it is being developed.  Descriptions of test cases and required scenarios/projects based on content from the remaining architecture description are examples of content we will put in this folder.
