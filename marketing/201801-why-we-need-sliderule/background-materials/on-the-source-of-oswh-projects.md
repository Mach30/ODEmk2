# On the Source of OSHW and What Projects Need to Store

_This material comes out of a number of sources including personal J. Simmons' personal OSHW projects, countless conversations about OSHW with [Matt Maier](https://github.com/matthewmaier) about [Howstr](http://github.howstr.com/), and a recent request at a meeting to define the minimum set of information required to store "source" of a hardware project.  To all that have contributed to these ideas in both large and small ways, thank you._

If you want to make something (anything from a craft project to a rocket) you need a minimum of two things:
1. The materials that will become the thing you are making
2. The instructions for assembling the materials into the thing you are making

Getting all of the above in one handy package is why IKEA furniture and DIY kits are so popular.  Open the package, find the assembly instructions, and off you go.

It turns out this is also true of open source software.  “But wait,” I hear you saying, “there are no materials in open source software, it’s all just source code.”  Oh, really?  

Let’s take a look at your average compiled code open source program.  To make your program you first download a compressed archive file (typically a .tar.gz or similar on Linux).  There is your package.  Next you expand the archive, or to put it another way you open the package for your DIY project.  If you look closely, you will find that the archive actually contains two different types of source files.  The first set is the set of files related to compiling the program (configure and make files at two common examples).  These are the build instructions for the program.  It just so happens these build instructions are intended to be followed by software instead of a person.  

This leaves us with the second set of source files, those that are the code that will be compiled into the actual program (the thing you are making).  These files are what we typically think of when we talk about the source code of a program.  And, if you look at the list of things you need to make something, it is clear that these source files are the materials you need to make the program, not the instructions you need to make the program.

But, if you ask most people, they will equate the “source code” with the instructions (probably because source code is a set of instructions, those that define the behavior of the program when it is running).  

An interesting observation that can be drawn once we understand this is that software version control systems are primarily tools for storing and distributing open source software materials, and only secondarily for storing and distributing assembly instructions.  In fact, the principle reason we can use the same storage system for the materials and assembly instructions is the happy coincidence of using plain text files as the medium for producing the materials (the source code) and the assembly instructions (configure/make files and the like).

This confusion between the materials of open source software and the assembly instructions (along with the happy coincidence of common medium for them) is likely the root of the difficulty in defining how we should capture open source hardware projects on the internet.  After all, it is not like we can store and distribute the materials for hardware projects in version control systems (or any digital storage system for that matter).  

Neither have we reached a point where we can just hand off the assembly of a hardware device to a piece of software (even 3D printing often involves a number of manual steps before the printer starts running and after a part is “finished”).  

So, we clearly need human oriented assembly instructions where open source hardware projects are concerned as humans are the “compilers” when we are talking about hardware.  For the time being, these assembly instructions will come in the form of documents.  Further, it is safe to assume the assembly instructions will need greater formatting than what can be accomplished in plain text files (we left plain text behind as the primary means of written expression long ago).  

This still leaves the the question of storing and distributing the materials for open source hardware projects.  Until Star Trek replicators are invented, we will have to accept a flexible definition for storing materials where open source hardware projects are concerned and focus on what we can store and distribute digitally.  Fortunately there is an obvious solution:  the bill of materials.  With a bill of materials, one can go to the appropriate suppliers and purchase the exact materials required for the project.  As an added bonus, the bill of materials can be expressed as another document, so we once again find ourselves with a happy coincidence where the materials and assembly instructions can be captured in the same medium, so we should be able to store and distribute them together using the same system.  

It turns out this “happy coincidence” is essential for ensuring the assembly process always works.  By storing the materials and assembly instructions together, we ensure they stay in sync without needing to use some system external to and separate from the storage system(s).  This simplifies the project management, making it more robust and reliable.  We will need to keep this observation in mind as we look at how to store and distribute open source hardware projects.

Let’s take things a step further, and look at making something out of two other things we have to make first (aka a project with sub-assemblies).  Let’s call them Thing1 and Thing2. Now we need the materials for the thing we are ultimately making (which includes Thing1 and Thing2), its assembly instructions, plus the materials and assembly instructions for Thing1 and Thing2.  If we look at all of these items in a list like the one at the beginning it would look something like this.


	1. Materials for our project
		1. Thing1
			1. Materials for Thing1
			1. Assembly instructions for Thing1
		1. Thing2
			1. Materials for Thing2
			1. Assembly instructions for Thing2
		1. (Possibly other materials for our project we can just purchase)
	1. Assembly instructions for our project

Now imagine Thing1 had its own nested sub-assemblies.  Clearly we would get another level of hierarchy.  This pattern would continue to repeat recursively until all of the sub-assemblies had been documented and we are left with a tree structure where all of the leaf nodes only contain lists of materials which can be purchased instead of being made.

Let’s run one more thought experiment.  What happens when we want to make an open source electronics project that takes sensor data and displays it on our computer?  Clearly we need to capture the list of materials and assembly instructions for each sub-assembly as well as the top level project.  But what are the sub-assemblies of a project like this?  Based on the material above, I would organize the sub-assemblies in the following manner.


1. Main project
	1. PC Software
	1. Electronics contoller
		1. Electronics case
		1. Electronics
			1. Main board
			1. Sensors
			1. Firmware

Which then leaves us with a data structure for our project like the one below.  Note. this structure leaves off the other materials for purchase items for brevity.


1. Main project
	1. Materials
		1. PC Software
			1. Materials (e.g. software source code)
			1. Assembly instructions (e.g. configure/make files)
		1. Electronics controller
			1. Materials
				1. Electronics case
					1. Materials (including cad files and bill of materials)
						1. ...
					1. Assembly instructions
				1. Electronics
					1. Materials
						1. Main board (possibly purchase like an Arduino)
						1. Sensors (purchased)
						1. Firmware
							1. Materials (firmware source code)
							1. Assembly instructions (make etc for firmware)
					1. Assembly instructions
			1. Assembly instructions
	1. Assembly instructions

  Notice in this example, our materials elements are a mix of hardware (captured in bills of materials) and source code (captured in text files).  Similarly, our assembly instructions are a mix of documents for the hardware elements and source files for the software elements.  As discussed above, we need to store all of these elements in the same storage system to provide for simple and robust synchronization of the materials and assembly instructions across the entire project.

  This last statement might sound like an argument for using software version control systems to store the project data for open source hardware projects.  And on the surface that idea looks promising.  Software version control systems have decades of development and research behind them.  They also support essential functions for sharing and collaboration (namely the ability to fork, branch, and merge projects).  But they also have some significant weaknesses where open source hardware development is concerned.


1. Everyone involved in the project has to learn how to use the software version tool of choice, which is a huge barrier to entry for non-programmers.  I have seen many engineers try to come to grips with tools like svn or git and it usually ends poorly.  Their workflow does not usually fit into the pattern of these tools (how does one diff a 3D CAD file anyway?) so they are really starting at a disadvantage when the storage system is one built for storing software source code.
1. Whereas the majority of content in software development is the materials (aka the source code), in hardware the majority of the development is in the assembly instructions (aka documentation) and users have come to expect the ability to develop documentation collaboratively either in the form of wikis or the live collaboration available in tools like Google Docs.  Offline editing and committing is just not an acceptable use case for documentation in the 21st century, especially with distributed teams on the internet.
1. TBD (pretty sure we have other things to say here)

Of course, the real challenge is that we need to mix collaboratively developed documentation with source code in the same storage system if we want to store all of the materials and assembly instructions for our open source hardware projects in the same storage system.  The trick then becomes structuring this data and presenting it in such a way that software developers see a familiar interface in the form of a software version control system when they are interacting with source code and that hardware developers see a familiar document, or better yet, content management system supporting online collaboration providing a simple interface to any foreign concepts such as forking, branching, and merging.

This is the ultimate goal of Sliderule.
