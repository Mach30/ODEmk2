# Sliderule
This is the current development repository for Sliderule (the foundation of Open Design Engine Mk 2).  The project is in the early stages of development, and as such we are focusing on the architecture and design of the new software.  See below for information on the project's motivations and how the repository is organized.

# Motivation
Mach 30 launched [Open Design Engine](https://opendesignengine.net) (ODE) in 2012.  Since then we have run our own OSHW projects on ODE, observed other groups host OSHW projects on ODE and other sites, and held numerous conversations on and offline about the nature of hosting OSHW projects.  

After much reflection, we have come to three conclusions about OSHW project hosting.  One, the OSHW community is still searching for a project hosting solution that meets the needs of hardware projects (where documentation is part of the source code).  Two, OSHW project hosting must support forking, merging, and branching of the entire project, not just its software components.  And three, (a lesson for all types of project hosting) time based browsing (that is being able to select a date/time and have all of the project content be consistently linked to that date/time when browsing the project's content) is needed to automatically support linking to specific versions/commits of the project.

Sliderule software will address all three of these conclusions as well as modernize the implementation of Open Design Engine.  Implementation improvements will include replacing the Ruby on Rails environment with Node.js and minimizing the features implemented in the core system to facilitate a more modular design.  

We will also be keeping the best parts of ODE.  These include sub-projects with all of the features of top level projects, a consistent and universal text editor/formatting, and being a single point for hosting all details of a project.

Please feel free to join us as we take the next step in OSHW project hosting.


# Repository Structure
The repository currently contains three top level folders to facilitate documentation of the system architecture and research.  These folders are:
* architecture - System architecture models and documentation
* resources - Documetation of potentially useful resources for architecting or implementing Sliderule.  Examples include lists of potential libraries, links to APIs or methodologies we may be considering, etc.
* planning - Planning documentation (e.g. backlog, sprint planning, reviews, retrospectives)
* src - the source code for Sliderule
* marketing - materials related to Sliderule marketing activities, typically stored in their own sub-folders.
