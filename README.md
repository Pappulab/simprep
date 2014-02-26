  simprep: overview
=======

**simprep** is a simple tool which allows you to take a single-letter amino acid sequece (raw or FASTA) and directly convert it into a CAMPARI ready, neutrally charged sequence with a specific salt concentration.


 usage
 ===

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

contact
===
For additional support, bug reports or anything else contact alex.holehouse@wustl.edu

  