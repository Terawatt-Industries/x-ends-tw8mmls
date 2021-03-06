#RepRap X-Ends for Terawatt Industries Leadscrew/Nut and LM8UU Bearings or Acetal Bushings
-----------------------------------------------------------------------------------------

This is a modified version of the popular prusa/mendelmax x-ends for use with acetal bushings from SDP and Terawatt Industries leadscrew/nut combination. It's based on the 1.1 x-end version at thingiverse.com/thing:21122. The only modifications are to allow for a flanged leadscrew nut and acetal bushings instead of LM8UUs.

If building from SCAD sources, note the assembly module's 'mode' parameter.  All prior modes from the original 1.1 are supported.


#Part Assembly Instructions
If you're not familiar with the x-axis of a reprap, you can learn more at reprap.org/wiki/Mendel_X-axis.

Assembly instructions for this part are like other x-ends, of which there are many variations. Refer to the excellent instrutions posted at reprap.org/wiki/LongboatPrusa#Instructions_11, note the variations in this part, and you should have enough to complete assembly. Let us know if you have questions!

There are two basic changes:
1) Substitutes a 8mm Terawatt Industries leadscrew for oft-used cheap drill rod. Uses a flanged nut that's bolted through with two bolts.
2) Uses acetal bushings with 17.5mm OD for the z-axis smooth-rod, typically 8mm. For example, the bushings at sdp-si.com/eStore/Direct.asp?GroupID=469

Note: The "repaired" STL file(s) corrects manifold mesh errors in the original source. All raw SCAD, STL, etc. are in the ZIP.

#Building STL from SCAD Source
An ANT script is provided for automated openscad compilation of source files in this project.  You must have ANT installed to use this build script.  ANT is based on Java and runs on Windows and Linux platforms.  The ANT build script provided with this project is a work-in-progress but it's actively used and maintained.

##Configuring ANT
The build.xml in the project depends on the Flaka ANT add-on.  To install Flaka in your environment, enter the following from a command line interface (unix):
cp [path-to-this-project]/tools/build/ant-flaka-1.02.02.jar [path-to-ANT-installation]/lib

In other words, Flaka installs like any other ANT add-on.  If you have trouble installing the library, or don't know where ANT is installed, try typing "ant -diagnostics" from a command line.

##ANT Targets
To list the targets provided by this build.xml enter "ant -p" from a command line interface.

##Building A Single Part Using ANT
To build the SCAD source files for the first time you must edit unix.settings.properties (or windows.settings.properties).  Set the path to the executable for openscad, for example (on OS X):
exec.path.oscad=/Applications/OpenSCAD.app/Contents/MacOS/OpenSCAD

Once you've edited unix.settings.properties run the following from a Unix or Windows command line to compile the SCAD source files:
ant

##Building Multiple Parts Using ANT
---------------------------------
Enter the following from a Unix or Windows command line to build 4 STL files.
cd [project-directory]
./tools/build/build-all-parts.sh

###Shell Parameters
To change the ZSTOP option (set to true by default), edit tools/build/ant_assembly.scad.tpl.  All other configuration 

We'll port the UNIX SH script to Windows BAT very soon - if you have one already please send it over!
=======

##Open Source Ancestors
1. [MendelMax 1.5 for LM10UU](http://www.thingiverse.com/thing:20355)
1. [X-Ends](http://www.thingiverse.com/thing:18384)

