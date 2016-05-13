# fix-prokka-header
Fixes the headers in genbank files (.gbk) generated by Prokka.  

##Author

Jason Kwong (@kwongjc)

##Usage

```
 fix-prokka-header.sh -h
Name:
  fix-prokka-header.sh
Author:
  Jason Kwong <j.kwong1@student.unimelb.edu.au>
Usage:
  fix-prokka-header.sh contigs.gbk > corrected.gbk
Parameters:
  contigs.gbk    Genbank file from prokka ie. file.gbk
Options:
  -h             Show this help
```

For some assemblies, when annotated by Prokka, the header joins the LOCUS name with the sequence length of that locus:

```LOCUS       SRR1661160_contig000001173535 bp   DNA     linear       09-MAY-2016```

This script amends this to the following (and for all other LOCUS headers in the file):

```LOCUS       SRR1661160_contig000001	173535 bp   DNA     linear       09-MAY-2016```

This fix is required by some programs that use .gbk files eg. Geneious, [Snippy](https://github.com/tseemann/snippy), [Nullarbor](https://github.com/tseemann/nullarbor), etc.  
The new .gbk file is printed to ```stdout```. To save to new file, redirect ```stdout```:

```$ fix-prokka-header.sh contigs.gbk > corrected.gbk```

##Bugs

Please submit via the [GitHub issues page](https://github.com/kwongj/fix-prokka-header/issues).  

##Software Licence

[GPLv3](https://github.com/kwongj/fix-prokka-header/blob/master/LICENCE)

##Links
* [Prokka](https://github.com/tseemann/prokka)