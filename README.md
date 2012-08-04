RepRap x-ends for Misumi Leadscrew/Nut and Acetal Bushings
----------------------------------------------------------

This is a modified version of the popular prusa/mendelmax x-ends for use with acetal bushings from SDP and Misumi leadscrew/nut combination. It's based on the 1.1 x-end version at thingiverse.com/thing:21122. The only modifications are to allow for a flanged leadscrew nut and acetal bushings instead of LM8UUs.

If building from SCAD sources, note the assembly module's 'mode' parameter.  All prior modes from the original 1.1 are supported.


Part Assembly Instructions
--------------------------
If you're not familiar with the x-axis of a reprap, you can learn more at reprap.org/wiki/Mendel_X-axis.

Assembly instructions for this part are like other x-ends, of which there are many variations. Refer to the excellent instrutions posted at reprap.org/wiki/LongboatPrusa#Instructions_11, note the variations in this part, and you should have enough to complete assembly. Let me know if you have questions!

There are two basic changes:
1) Substitutes a 8mm Misumi leadscrew for oft-used cheap drill rod. Uses a flanged nut that's bolted through with two bolts.
2) Uses acetal bushings with 17.5mm OD for the z-axis smooth-rod, typically 8mm. For example, the bushings at sdp-si.com/eStore/Direct.asp?GroupID=469

Misumi Leadscrew: MTSKR8
Misumi Nut: MTSFR8


Note: The "repaired" STL file(s) corrects manifold mesh errors in the original source. All raw SCAD, STL, etc. are in the ZIP.


Source Code Compilation
-----------------------
An ANT script is provided for automated openscad compilation of source files in this project.  You must have ANT installed to use this build script.  ANT is based on Java and runs on Windows and Linux platforms.  The ANT build script provided with this project is a work-in-progress but it's actively used and maintained.

Configuring ANT
---------------
The build.xml in the project depends on the Flaka ANT add-on.  To install Flaka in your environment, enter the following from a command line interface (unix):
cp [path-to-this-project]/tools/build/ant-flaka-1.02.02.jar [path-to-ANT-installation]/lib

In other words, Flaka installs like any other ANT add-on.


Building
--------
To list the targets provided by this build.xml enter "ant -p" from a command line interface.

Targets:
compile_scad_to_stl -- (default) compile src/*.scad -> dist/*.stl using OpenSCAD executable *release-candidate
pack_everything -- GZIP all  *broken=wip
pkg_dist_files -- GZIP STL files in /dist *broken=wip


To build the SCAD source files first set/verify unix.settings.properties (or the windows analog).  Set the path to the executable for openscad, for example (on OS X):
exec.path.oscad=/Applications/OpenSCAD.app/Contents/MacOS/OpenSCAD


Once you have unix.settings.properties properly setup run the following from a Unix or Windows command line to compile the SCAD source files:
ant

IMPORTANT!
----------
The SCAD files contain variables/parameters that define the parts being built.  This ANT script has no way to change them to build the entire set of parts you may need.  You can use a simple notepad/VI editor for this if there are multiple parts to build.  We're working on automating this aspect of the build so that SCADs have external configuration which provide hooks for ANT to parametrize the SCAD compilation.