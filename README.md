# GBM_circs
circRNA analysis in glioblastoma multiforme

This repo does not contain large files. To obtain genome reference, gtf and circRNA sequences you have to:
1/extract all .7z files
2/run code in lines 63-76 from ./scripts/Fig1.Rmd

To obtain miRNA binding sites you have to obtain circRNA sequences (as mentioned in previous line) and then run:

sed ‘s/>//g’ < ./circ_seqs/GBM_and_brain_all.fa | sed ‘s/T/U/g’ | sed 'N;s/\n/\t9606\t/' > ./miRNA/GBM_and_brain_all.txt

perl ./miRNA/targetscan_70.pl ./miRNA/humanMirsTargetscan.tsv ./miRNA/GBM_and_brain_all.txt ./miRNA/miR_binding_sites.txt

This analysis may take a few hours or even days.
