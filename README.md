build_install_script_for_gemrb
==============================

## Build and install script for [gemrb](https://github.com/gemrb/gemrb)

Please note there are two scripts in the repository:

build_gemrb

build_gemrb_sh_version

The latter script runs with sh instead of Bash. I have tested it with dash, 
but it may need to be tweaked for very old implementations of sh. I include it
so that the option is available for those who don't use Bash.

This script installs any dependencies for gemrb, which is 
an open source recreation of the infinity engine (see 
[the official site](http://www.gemrb.org)), and then compiles the program when 
run for the first time using the -i switch. After that, gemrb 
can then be updated or rebuilt at any time.
          
    
## All options:

    -d      diagnostic mode, follow script execution 

    -h      show this help file

    -v      In verbose mode all stdout and stderr is printed and a logfile is created in $HOME
            
    -q      quiet mode; no output at all. Not compatible with -i and -p options as the user needs to 
            respond to a question and so it will be ignored for those modes even if chosen

    -u      update (git pull) source folder and compile again if necessary 

    -i      compile and install from scratch (dependencies are checked also)

    -p      check (and install) essential dependencies and then exit

    -l      show GPL license and version info



## Notes:

The script will run on any Linux based system, but the dependencies will only be installed if Debian, Mint or Ubuntu is detected.
This is because the package names are common across those Debian based systems, but may need to be updated in the future.

Other distros will have different packaging systems, or one may need to compile the dependencies from source.
For more general information on gemrb and installation, see [the official site](http://www.gemrb.org/wiki/doku.php?id=installation)

Requires GNU Bash version of at least 3.1.

Make the script executable (`chmod u+x`), place it in a `$PATH` location, or run as

    ./build_gemrb [options]

## Useful Examples:

These examples assume that you are running build_gemrb from its directory, and that it 
isn't in `$PATH`.

## Just check dependencies and install if necessary

    ./build_gemrb -p

## New install

    ./build_gemrb -i 

## Update installation

    ./build_gemrb -v -u 

## Bugs

Report to [github](https://github.com/Exactus29/build_install_script_for_gemrb/issues) or email <exactus29@gmail.com> 
