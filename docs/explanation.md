<!-- This part of the project documentation focuses on an
**understanding-oriented** approach. You'll get a
chance to read about the background of the project,
as well as reasoning about how it was implemented. -->


<!-- > **Note:** Expand this section by considering the
> following points:

- Give context and background on your library
- Explain why you created it
- Provide multiple examples and approaches of how
    to work with it
- Help the reader make connections
- Avoid writing instructions or technical descriptions
    here -->

<!-- Installation -->
<!-- ============ -->

Installation of ``EStA`` is super easy provided you have necesarry python packages already installed
in python3 environment (python 2 not supported).

- To install, just go the source directory, and execute the install.sh file as:
``` 
./install.sh
```


- or simply, type the following:
```py
python setpy.py install --user
```
This will install the `EStA` in your local directory.



EStA contains various software preprocessing and postprocessing routines to make 
  tasks easily and automated to some extents.



One class is `Xat` OR `aadhaar` class to handle atomic structure information i.e. atomic positions, atomic
    symbols, cell parameters. It can handle both molecules and periodic systems. Molecules are handled
    using xyz file format and periodic systems are handled using POSCAR file format. These formats can
    be further suited to other file format,
    Various Bags are present in the EStA folder to handle software specific data such as `vaspBag`, `qeBag`,
    `siestaBag`, `OrcaBag`, `grrmBag`, `xtbBag`, and so on.

Thermodynamics can be calculated based on the vibrational calculation implemented in the `qeBag`. Similarly
    transition state analysis is possible using routines in the `transitionState`.
    There are lots of routines some written in fortran to be interfaced with `EStA` package. Machine learning
    algorithms are also implemented such as GPR based on gaussian processes in the `mlBag`.


Try to excess the aadhaar class in the general directory and then you can access atomic and poscar atoms 
  informations. Also in vaspBag.inout, try to access the crystal lattice class for poscar file.

<span style="color:blue">
**Note**
</span>

1. Atom/atoms are handled by `Xat` aka `Aadhaar` class.
2. Crystal lattice (atoms and lattice) is handled by the `Xlat` aka `CrystalLattice` class.
