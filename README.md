# formula 2.0
Formal Specifications for Verification and Synthesis

## Building FORMULA

In order to build FORMULA you must acquire and build dependencies.
These dependencies are not part of the FORMULA project, though
the FORMULA build scripts offer assistance in downloading and compiling
other Codeplex dependencies. 

## Non-Codeplex Dependencies

You must acquire and install these yourself.

1. Microsoft .NET 4.5 (http://www.microsoft.com/en-us/download/details.aspx?id=30653)
2. Visual Studio 2012 or 2013 (The free "Express" version is acceptable http://www.visualstudio.com/downloads/download-visual-studio-vs#d-express-windows-desktop)
3a. Python 2.7.5 - to build dependencies (http://www.python.org/download/releases/2.7.5/)
3b. "python" must be in PATH
4.  OPTIONAL: Visual Studio SDK to enable VS-integrated code generation. Not available for VS Express.  

## Codeplex Dependencies

The FORMULA build scripts will try to automatically download these dependencies from Codeplex.
Or you may compile the dependencies manually and place them in the required locations. 

1. Gardens Point Scanner Generator (http://gplex.codeplex.com/)
2. Gardens Point Parser Generator (http://gppg.codeplex.com/)
3. Z3 SMT Solver (http://z3.codeplex.com/)

To *automatically* download and compile any missing Codeplex dependencies open a command
prompt (cmd.exe):

    cd Somewhere\Formula\Bld
    built.bat

As long as dependency artifacts are detected, then build.bat will not try to rebuild them.
If you delete external dependencies from Somewhere\Formula\Ext, then this will be detected
and rebuild will occur. You can also force all dependencies to be re-acquired and rebuilt by:

    cd Somewhere\Formula\Bld
    built.bat -e

To *manually* download and compile dependencies open a command prompt:

    cd Somewhere\Formula\Bld
    built.bat -l

The "-l" option lists the URLs to download the required sources and lists where the compiled artifacts
must be placed in order for FORMULA to find them.  

## Compiling FORMULA

Release version - open a command prompt:

    cd Somewhere\Formula\Bld
    built.bat

Debug version - open a command prompt:

    cd Somewhere\Formula\Bld
    built.bat -d

Outputs of the build are placed in Somewhere\Formula\Bld\Drops

## Running regression tests

    cd Somewhere\Formula\Tst
    test.bat

As a side effect, FORMULA will be rebuilt with build.bat -d and
regressions will be run against the x86 debug version placed in the Bld\Drops folder.
