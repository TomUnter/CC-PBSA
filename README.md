# CC PBSA



## Installation

1. Download the repository.
2. Use anaconda to make a python environment for CC/PBSA (python >= 3.7)
3. Install pymol into the environment (conda install -c conda-forge -c schrodinger pymol-bundle)
4. Download and install Gromacs = 2019.3 (higher than that will currently not work)
   Follow and check installation 
5. Download Concoord and follow the installation (https://www3.mpibpc.mpg.de/groups/de_groot/concoord/index.html)
6. Download GroPBS and follow the installation (https://github.com/fkranz/GroPBS)
   Make sure ./gropbe is executable. It depends on dynamic Gromacs libraries, so export LD_LIBRARY_PATH="/path/to/gromacs/lib:$PATH"
   This should fix any appearing problem.
7. Now install the package with (python setup.py install --user)
   This will download necessary packages for the environment and set up flags files for running
8. Now go in ccpbsa/parameters and open the flags files. You need to specify the executables for at least Gromacs and GroPBS
   If Concoord's dist and disco need to be globally defined, but they should be by default after installation.
9. Start the program with python ccpbsa routine **kwargs

## Running the program

Inside the ccpbsa folder the file ccpbsa is the executable.
The minimum input needed for stability calculations is:
python path/to/ccpbsa stability -w wt.pdb -m mutations.txt
Everything else, such as triplet table, .mdps for Gromacs etc. will be taken automatically.

The minimum input for affinity calculations is:
python path/to/ccpbsa stability -w wt.pdb -m mutations.txt --chains ABC


A more extensive guide to all arguments will be added. For now orientate through the help command.

