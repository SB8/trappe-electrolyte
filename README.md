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

## Atom type naming scheme

## Tabulated parameters (WIP)

### Bond lengths


| Molecules | Bond | r<sub>b</sub> [nm] | Ref |
|---|---|---|---|
| EC, PC | O1=C2 (O=C) | 0.12  | [2] |
| EC, PC | C2-O3 (C-O) | 0.136 | [4] |
| EC, PC | O3-C5 (O-CH<sub>2</sub>) | 0.143 | [4] |
| EC     | C5-C6 (CH<sub>2</sub>-CH<sub>2</sub>) | 0.152 | [4] |
| PC     | O4-C6 (O-CH) | 0.145 |  |
| PC     | C5-C6 (CH<sub>2</sub>-CH) | 0.153 |  |
| PC     | C6-C7 (CH-CH<sub>3</sub>) | 0.151 |  |

Note: Very similar bond types (e.g. EC CH<sub>2</sub>-CH<sub>2</sub> and PC CH<sub>2</sub>-CH) could be combined in a future release

### Angles

### Dihedrals

## References

[1] J. Phys. Chem. B 2004, 108, 17596-17605 (TraPPE-6 ethers/glycols)

[2] J. Phys. Chem. B 2009, 113, 6415–6425 (TraPPE acrylate)

[3] J. Phys. Chem. B 2012, 116, 11234−11246 (TraPPE cyclic ether)

[4] J. Phys. Chem. B 2004, 108, 2016-2027 (Masia EC)

