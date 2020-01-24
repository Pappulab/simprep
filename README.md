simprep: overview
=======

**simprep** is a simple tool which allows you to take a single-letter amino acid sequece (raw or FASTA) and directly convert it into a CAMPARI ready, neutrally charged sequence with a specific salt concentration.



Usage
-------------
Simprep is designed to be used in *nix environments - i.e. it should run on any flavour of Linux or OSX. Given its just a Python script no installation is required - simply download and run the script here.

To use simprep simply run as follows. This generates a file called seq.in in your current directory, as well as printing some information to the terminal
 

    ./simprep -f <sequence file> -s <salt conc in M>  -v <additional space>

`<sequence file>`

A file containing the 1 letter amino acid code for your sequence of interest. This can be a raw file or a fasta file. e.g.

    >my snazzy sequence in fatsa format
    MIQKTPQIQVYSRHPPENGKPNILNCYVTQFHPPHIIQMLKNGKKIPKVEM
    SDMSFSKDWSF
    YILAHTEFTPTETDTYACRVKHASMAEPKTVYWDRDMKKKK

`<salt conc>`

The target concentration in Molar (i.e. 0.010 is 10 mM)

`<additional space>`

The only non-explanatory option here is the additional space option. CAMPARI simulations run inside a spherical droplet. **simprep** calculates the optimal droplet radius by estimating a fully extended chain is 4 Angstroms * (number of residues+1). The reality is that a chain never reaches this fully extended size, but to avoid finite size artefacts it seems sensible to over-estimate rather than under-estimate.

That said if you want to over-estimate *even more* then the -v option allows you to add some number of additional Angstroms between the end of your fully extended chain and the droplet edge.

Considerations
-------------
Below are a couple of things you may wish to consider when running simprep

* Getting the correct salt concentration *entirely* depends on YOU setting FMCSC_SIZE variable in your keyfile to the calculated radius value.

* Ion-based calculations scale with n-squared. What this means is the simulation time grows very rapidly as the number of ions increases, so consider using lower salt concentrations if possible

* Histadine can have an epsilon-carbon hydrogen (HIE) or a delta carbon hydrogen (HID). By default simprep used HIE, so if this maters you may want to change the seq.in file created appropriatly

* By default we use NaCl for salt. If there is interest in using other salts (which exist in ABSINTH) let me know and I can add support for this

* The actual salt concentration is given when you run the program, but TOTALL

Contact
-------------
For additional support, bug reports or anything else contact alex.holehouse@wustl.edu

  
