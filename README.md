# 2015-pseudo

Repository containing raw data, scripts and circos configuration files to reproduce the genome plot.

#### Main data
File | Description | Method summary
--- | --- | ---
`Pseudo_Pac.fas` | Genome sequence | Assembled with `RS_HGAP_Assembly.1` in SMRTanalysis 2.0.1, then manually cut and aligned
`Pseudo_Pac.gtf` | Genome annotation | Annotated in GenDB with default settings
`modifications.gff3` | Modified bases | Methylation detection with `RS_Modification_and_Motif_Analysis.1` in SMRTanalysis 2.0.1, using `Pseudo_Pac.fas` as the reference

#### Scripts etc.
File | Description | Method summary
--- | --- | ---
`circos.conf` | Main CIRCOS configuration | Requires CIRCOS to run: http://circos.ca/software/download/circos
`gcSkew.pl` | Calculate GC content and skew | Modified from: https://github.com/Geo-omics/scripts/blob/master/AssemblyTools/gcSkew.pl 

#### Temporary files
File | Description | Method summary
--- | --- | ---
`gc_5000.gcSkew` | GC content and skew | Output of `gcSkew.pl -f Pseudo_Pac.fas -w 5000`
`gc_5000.gc` | Raw GC content | Column with the GC content, taken from `gc_5000.gcSkew`
`gc_5000-62.46.gc` | Adjusted GC content |  Absolute distances from the genome's mean GC content (62.46%)
`gc_5000.skew` | GC skew | Column with the GC skew, taken from `gc_5000.gcSkew`
`genes_heat_*.txt` | Methylation per gene | Relative methylation per gene, seperately for genes on plus and minus strand
`modifications_*.txt` | Genome-wide methylation | Absolute methylation per 2kb, 10kb and 50kb window, also strand-specific
Anything else | Mandatory CIRCOS files | Stuff like genome length, layout options, ...
