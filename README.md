# trappe-electrolyte
 Extension of the TraPPE force field to carbonate electrolyte solvents

## Molecule abbreviations

| Abbreviation | Molecule |
| --- | --- |
| EC  | Ethylene carbonate |
| PC  | Propylene carbonate |
| DMC | Dimethyl carbonate |
| DEC | Diethyl carbonate |
| DME | Dimethoxyethane |

## Folder structure

### forcefield

ffnonbonded.itp contains the mass and Lennard-Jones parameters of each atom type. The charges in this file are generally overwritten by the charges given in the molecule-specific itp files.
ffbonded.itp contains parameters for bond, angle and dihedral interactions. Dihedrals use Gromacs type 3 (Ryckaert-Bellemans or OPLS form).

### itp

This contains molecule-specific itp files, which specify the atom names, charges and bond connectivity for each molecule. Gromacs locates the parameters for the bonded interactions from ffbonded.itp (in the forcefield folder).

### pdb

Files containing atom coordinates of each molecule. The order of the atoms in these files should match the corresponding itp files.

### mdp

Gromacs molecular dynamics parameter (mdp) files. mdp_NPT_eq.mdp is for equilibration and will generate initial atom velocities and use the Berendsen barostat.

