# System Architecture Documetation
This folder contains the system architecture description for ODE mk 2.  Its structure is based on the Four Pillars of SysML, with some Agile methods thrown in.  We will be following a process where we start with the behavior of the system.  We will derive requirements and PBIs (stored in the backlog under the project's planning directory) from the described behaviors.  From there we will determine the structure of the system (defining the elements which will implement the system) and how to test the system.

# Architecture Folder Structure
We will store documentation for each of the pillars in the following, separate folders.

1. behavior - This folder contains descriptions of how the system should operate and how users should interact with it. User stories and CONOPS are two examples of content we will put in the behavior folder.
2. requirements - This folder contains formal requirements for the system.  Given our use of Agile methods, this folder may end up sparsely populated with preference going to the development of PBIs.
3. structure - This folder contains the structural description of the system.  Block diagrams, narative descriptions of the elements of the system, and information on how the ODE mk 2 software interacts with users and external resources are examples of conent we will put in the structure folder.  During architecture development, expect to see multiple possible implementations documented and discussed.
4. analysis - This folder contains documentation on how to verify and validate the system as it is being developed.  Descriptions of test cases and required scenarios/projects based on content from the remaining architecture description are examples of content we will put in this folder. 
