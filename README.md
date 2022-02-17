## Repository contents

The repository contains LaTeX files for compiling the PySIMM tutorial paper to be submitted to LiveCoMS journal. The paper describes best practices of work with PySIMM and particularly discusses the construction of polymer chains with specific tacticity.


## Guide to setup the examples for a test run

 ### Method 1: using Docker:
1. Clone the pysimm repository to any path on your computer:
```bash
git clone https://github.com/polysimtools/pysimm.git
```

2. Make a Docker image using dockerfile in the root of the freshly cloned repository
3. Run the image in a bash mode and clone examples:
```bash
git clone https://github.com/AlleksD/pysimm_lcms_guide.git
```

 ### Method 2: without using Docker:
1. Clone the examples from the repository to any path on your computer
```bash
git clone https://github.com/AlleksD/pysimm_lcms_guide.git
```
2. Clone the [pysimm](https://github.com/polysimtools/pysimm) repository to any other path on your computer
3. Depending on whether LAMMPS is installed in your working environement or not, do either (i) or (ii):
    1. If your working environement already has LAMMPS; make sure it contains the following packages: 
       * **class2** 
       * **extra-molecule** 
       * **kspace** 
       * **manybody** 
       * **misc** 
       * **molecule** 
       * **qeq** 
       * **rigid** 
       * **user-misc**[^1]
       
       to check the presence/absence of packages run: ``` lmp_machine -h```, where `lmp_machine` is the name of your LAMMPS binary
    3. If your working environement does not have LAMMPS installed; clone and install LAMMPS with all necessary packages (necessary packages are marked bold in the previous point).
6. Add environmental variables (to connect installed LAMMPS to pysimm, and to register pysimm in Python library):
```bash
export PYTHONPATH=$ PYTHONPATH;/path/to/pysimm
export PATH=$ PYTHONPATH;/path/to/pysimm/bin
export $LAMMPS_EXEC=/path/to/lammps/binary
```

[^1]: Recentely LAMMPS developers renamed some package, so if you use LAMMPS version later that 03mar2021 *there is no user-misc package present in the library*
