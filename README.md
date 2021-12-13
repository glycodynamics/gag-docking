# Docking
This tutorial aims to dock glycans and glycosminoglycans to proteins using the [AutoDock Vina](https://vina.scripps.edu), [Vina-carb](https://pubs.acs.org/doi/10.1021/acs.jctc.5b00834) and [GlycoTorch Vina](https://pubs.acs.org/doi/10.1021/acs.jcim.0c00373)
You can download all the input files by clicking in Code --> Download Zip. Unzip this file and go inside docking directory. 
We will breakdown this tutorial in five steps.

## 1. Structure Preperation
In this tutorial we will be docking a Heparan sulfate (HS) etrasaccharide to human HS 3-O-sulfotransferase isoform 3 (3-OST-3), a key sulfotransferase that transfers a sulfuryl group to a specific glucosamine residue in HS. Firt of all, download X-ray structure of the complex from PDB [PDB ID: 1T8U] (https://www.rcsb.org/structure/1t8u). Now, open the PDB Structure in PyMOL and perform following structure manipulations:
#### remove crystal waters: 
Open 1t8u.pdb fil in PyMOL and click non on Action --> remove waters
#### save ligand and protein selerately
Now split the complex in protein and HS and save them seperately in two seperate pdb files. 
Select HS tetrasaccharide by clicking left mouse button on each monosaccharide. Then click on File --> export molecule --> Selection (sele) --> Save File name: ligand --> Files of type: pdb --> save

Now select all the co-crystalized ligands and remove them (Action --> remove atoms). Then save protein: File --> export molecule --> Selection (1t8u) --> Save File name: receptor --> Files of type: pdb --> save

These files have been prepared and placed under gag-docking direcotry. 

## 2. Preperation of reseptor and ligand PDBQT files
module load mgltools/v2.1.5.7
prepare_pdb_split_alt_confs.py -r receptor.pdb
prepare_receptor4.py -r receptor_A.pdb -o receptor.pdbqt -A "hydrogens"
prepare_ligand4.py -l ligand.pdb -o ligand.pdbqt -A hydrogens

## 3. Docking input files
## 4. Docking
## 5. Analyzing Docking Results
