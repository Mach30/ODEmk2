# Defining Advanced OSHW Projects

In _On the Source of OSHW and What Projects Need to Store_, we identified two things as required to make a thing.

1. Materials (in the form of Bills of Materials and Source Code)
1. Assembly instructions

This structure can recurse for sub-assemblies,  capturing all of the materials and assembly instructions required to go from off the shelf components to the finished project.  And for many open source hardware projects this list is sufficient to fully define a project.

But, as open source hardware pushes into fields requiring higher degrees of engineering rigor, the list above will become insufficient to fully define a project.  The following are additional items that may need to be added to the list to increase engineering rigor.

#### Operating instructions
Some projects need no explanation about how to use them (everyone understands what a shelf is for).  But others will not function if the required steps are not followed in the prescribed order.  Worse, some projects are not safe if not used properly.  These projects must include operating instructions in their list of required items to make them.

#### Requirements and Verification Instructions
Even something as seemingly simple as a chair or a table can benefit greatly by the addition of requirements (the chair will support an adult weighing at least 200 lbs).  And requirements are of no value without accompanying verification instructions (after assembly the chair weight capacity will be tested by stacking bar bell weights on the seat in 50 lb increments until the chair is holding 200 lb of weights).  In the case of software, verification instructions often take the form of automated tests.

#### Rationale/Analysis
For simple projects, development often follows a pattern of build and test (aka trial and error) with grater experience leading to fewer build/test cycles.  But, as projects become more complex and more expensive to build or test, analysis (and accompanying documentation of the analysis in the form of rationale) substitute for much of the build/test activity.  Analysis should be included in project data when it drives design decisions so it can be reviewed in the advent of a verification or operation failure.  Including analysis also enables future contributors to learn from past work and get up to speed more quickly.

It should also be noted that the development of rationale/analysis often emerges in communication channels.  Therefore, it is best to capture team communications inside the project data to facilitate marking threads/comments as rationale/analysis instead of having to remember to copy this data back into the project later.

#### Complete List of Project Data
Taken together, this leaves us with the complete set of project data as follows (the minimum project data is marked in **bold**).

1. Requirements
1. Rationale/Analysis
1. [Team Communications]
1. **Materials**
	* Bill of Materials
	* Source Code
1. **Assembly Instructions**
1. Verification Instructions
1. Operating Instructions

In general one should expect this list to be recursive for each sub-assembly.  
