This part of the project documentation focuses on **examples** usage of `EStA`.

<!-- > **Note:** Expand this section by considering the
> following points:

- Help newcomers with getting started
- Teach readers about your library by making them
    write code
- Inspire confidence through examples that work for
    everyone, repeatably
- Give readers an immediate sense of achievement
- Show concrete examples, no abstractions
- Provide the minimum necessary explanation
- Avoid any distractions -->



<!-- __Let us try out some of the capabilities of the EStA program with some examples below__ -->




--- 
## General related
- Read `xyz` file data. 

!!! example

``` py

#import esta.general.aadhaar as aadh  [this also works]
#aad = aadh.Aadhaar()

from esta import Xat # import Xat class
Xat.read_xyz(filename='x.xyz')
```


- Substitution of atoms by other atom or gp of atoms.

!!! example

```py
import glob
import esta.general.substitute_atom as substitute

atomid = 10
xyzfile = 'path_0000.xyz'
xyz_subs_file = 'methyl.xyz'  # taken from lib_xyz in esta

# atomid = 62
# xyzfile = 'de_SUB_path_all_all.xyz'
# xyz_subs_file = 'H.xyz' 

atom_id_subs = 1  #Generally.. C-atom Must be the first atom in the substituent 
part 

print('list of files: {}'.format(xyzfile))

substitute.substitute_atom_by_atoms(atomid=atomid, atom_id_subs=atom_id_subs,\
xyzfile=xyzfile, xyz_subs_file=xyz_subs_file)
```



- Read `poscar` file data.

!!! example
  
``` py

import esta.vaspBag.inout.crystal_lattice as clatt
xlatt = clatt.Crystal_Lattice("POSCAR", ''./)
# or xlatt=clatt.CrystalLattice()
xlatt.read_poscar()
print('atomic positions: {}'.format(xlatt.tau_cartesian))
print('atomic positions in crystal coordinates: {}'.format(xlatt.tau_direct))

xlatt.get_cell_matrix
#array([[7.35205746, 0.        , 0.        ],
#       [3.67602873, 6.36706853, 0.        ],
#       [3.67602873, 2.12235618, 6.00292978]])

xlatt.get_cell_vectors
#(array([7.35205746, 0.        , 0.        ]),
# array([3.67602873, 6.36706853, 0.        ]),
# array([3.67602873, 2.12235618, 6.00292978]))

xlatt.LV1
#array([7.35205746, 0.        , 0.        ])

xlatt.LV3
#array([3.67602873, 2.12235618, 6.00292978])

xlatt.real_volume
#281.0034678144921 in A^3

# print each atom type
xlatt.get_each_atm_type
#[1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3]

# print no. of atoms of each type
xlatt.get_natm_type
#array([ 4,  4, 14])

*Similary other method of the xlatt object can be excessed; currently all available methods are:*
# 'atm_type', 'each_atm_type', 'filename', 'get_all_atoms_labels', 'get_atm_type', 'get_cell_matrix',
# 'get_cell_vectors', 'get_dispPOSCAR', 'get_each_atm_type', 'get_grouped_list', 'get_natm_type',
# 'get_neach_type', 'get_poscar', 'get_rVolume', 'get_reciprocal_lattice', 'get_selectivePOSCAR',
# 'get_unique_list', 'is_cartesian', 'is_crystal', 'is_selective_dynamics', 'l_SelectDynamics',
# 'l_crystal', 'location', 'natm_type', 'natoms', 'read_poscar', 'real_volume', 'reciprocal_lattice',
# 'tau_cartesian', 'tau_cartestain', 'tau_direct', 'to_cartesian', 'to_crystal'

```


- Rename_files_using_index_for_ANY (collection of xyz or poscar files).

!!! example

``` py
 
import glob
import esta.general.rename_general as rename

#files = glob.glob("SUB_de_SUB*.xyz")
files = glob.glob("rlx*.xyz")

#--for keeping  part of the file--for example: [0,-2] part is kept ; last part is removed
first_index=False # if false mean 2nd index is also taken!
str_indx = [0,-2] #,[4,-2]] #  for first_index = False
#str_indx = [[0,-2] ,[4,-2]] #  ALSO can be used**

#--for removing begining part of the file--for example: [0,3]; this part is removed; last is kept
#first_index=True 
#str_indx = [0,3] #   for first index=True


for ifile in files:
    print('ifile is: {}'.format(ifile))
    rename.to_file_any(ifile, str_indx, first_indx_only=first_index, file_extension='xyz') #POSCAR' ) 
```




## VASP related

- Create input file for the vasp calculations.

!!! example

``` py

import esta.vaspBag.vaspin as vaspin
vaspobj = vaspin.vasp()
vaspobj.get_vasp_input(poscar_name='POSCAR')

```


---

- Read POSCARs for reactants and products in a reaction and generate intermediate structures.

!!! example

``` py

import numpy as np
from  esta.vaspBag.inout.crystal_lattice import CrystalLattice
import esta.general.get_configs as get_configs

output = CrystalLattice(filename = 'ach3oh_00_POSCAR', location = "./")
output.get_poscar()
atompositions = output.tau_cartesian

output2 = CrystalLattice(filename = 'cxyz_POSCAR', location = "./")
output2.get_poscar()
poscar_obj2 = output2 #.get_poscar()
atompositions2 = output2.tau_cartesian
N = 9
configurations = get_configs.get_atomic_configurations(N, atompositions, atompositions2)
print(configurations[1])

get_configs.get_poscar_images(N, poscar_obj, poscar_obj2)
```

---










<!-- - read `csv` file contents.
``` py

import numpy as np
import csv
csvfile = 'test.csv'
# csvfile = 'output.csv'
# with open('test.csv') as csvfile:
l = []
with open(csvfile) as csvfile:
    reader = csv.reader(csvfile)
    # reader_ = csv.reader(csvfile)
    for i, row in enumerate(reader):
        # print (i, row[1:-1] )
        if i > 0:
            sym1=row[1].split('_')[2]
            sym2=row[1].split('_')[3]
            print(i, sym1, sym2 )
``` 
-->


## Quanutm-Espresso related
- Create qe input file for QE calculations with option 1*

!!! example

``` py

import glob
import esta.qeBag.gen_qeinput_advv as gen_qeinput

ps_info = ('pbesol', '_v1.*')

posfiles=glob.glob('*POSCAR')
for ifile in posfiles:
    gen_qeinput.get_qe_input(ifile, ps_info, lprint_cell ='angstrom',\
    cal_type='vc-relax', lcopy_pseudo=True, l_pseudo_GVRB=True)
```




- Generate displacements from atomic positions in the poscar for vibrational calculations.

!!! example

``` py
import numpy as np
import esta
import esta.phonon.atm_displacements_selective_general_disp  as atmdisp

print('generating postion* files for displacement of selected atoms')
qe_part_file='qe_part'    #<-------not need to get poscar file s........MAKE It better ....TODO
posfile='fix_3_init_bi_POSCAR' #fix_rlx_3_4c_1_1e_POSCARPOSCAR'
delta_x = 0.02 # ang
atmdisp.gen_disp(posfile, qe_part_file, delta_x)
```


## ORCA related files
- Create ORCA input files for atomic relaxation from many xyz files: opt calculations

!!! example

  ```py


  import glob
  import esta.orcaBag.input_orca as iorca
  import numpy as np

  cal_type = 'OPT' 

  nproc='10'
  memory='1000'

  #-----functional and basis(may contain additional tags) together-----------
  functional = "BP86"
  basis = " def2-SVP def2/J RIJCOSX "


  #-----None, True, or exact words-------------------------------------------
  dispersion='D3Zero' #True or None  # always needed!!

  #-----None or some solvent-------------------------------------------------
  solvent=None

  #-----None or some txt-----------------------------------------------------
  #extra_tags = {'tag1': 'int=ultrafine','tag2':'nosymm'}
  extra_tags = {'tag3':'NoUseSym '}

  #---charge and spin multiplicuty=2S+1 ; for unparied e- => spin-multi = 2; 
  #  unpaired=1
  charge  = 2
  multiplicity = 2
  #--------------------------------------------------------------------------

  xyz_file_list = glob.glob("*.xyz")
  print('xyz files are:', format(xyz_file_list))

  for ii in xyz_file_list:
      print('--**--**'*10)
      orca_obj = iorca.GenerateInp(ii, charge, multiplicity, cal_type)
      orca_obj.write_inp(functional=functional,basis=basis,dispersion=dispersion,\
              nproc=nproc, memory=memory, solvent=None, extra_tags=extra_tags)
  ```






<!-- !!! orca_input

    ===  "Create ORCA input files for atomic relaxation from many xyz files: opt calculations"

        ```py

        import glob
        import esta.orcaBag.input_orca as iorca
        import numpy as np

        cal_type = 'OPT' 

        nproc='10'
        memory='1000'

        #-----functional and basis(may contain additional tags) together-----------
        functional = "BP86"
        basis = " def2-SVP def2/J RIJCOSX "


        #-----None, True, or exact words-------------------------------------------
        dispersion='D3Zero' #True or None  # always needed!!

        #-----None or some solvent-------------------------------------------------
        solvent=None

        #-----None or some txt-----------------------------------------------------
        #extra_tags = {'tag1': 'int=ultrafine','tag2':'nosymm'}
        extra_tags = {'tag3':'NoUseSym '}

        #---charge and spin multiplicuty=2S+1 ; for unparied e- => spin-multi = 2; 
        #  unpaired=1
        charge  = 2
        multiplicity = 2
        #--------------------------------------------------------------------------

        xyz_file_list = glob.glob("*.xyz")
        print('xyz files are:', format(xyz_file_list))

        for ii in xyz_file_list:
            print('--**--**'*10)
            orca_obj = iorca.GenerateInp(ii, charge, multiplicity, cal_type)
            orca_obj.write_inp(functional=functional,basis=basis,dispersion=dispersion,\
                    nproc=nproc, memory=memory, solvent=None, extra_tags=extra_tags)
        ``` -->





<!-- 
        ``` markdown
        * Sed sagittis eleifend rutrum
        * Donec vitae suscipit est
        * Nulla tempor lobortis orci
        ```

    === "Ordered List"

        ``` markdown
        1. Sed sagittis eleifend rutrum
        2. Donec vitae suscipit est
        3. Nulla tempor lobortis orci
        ``` -->
