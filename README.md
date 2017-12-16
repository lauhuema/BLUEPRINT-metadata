# BLUEPRINT-metadata
Ontology annotation of a subset of cell types from the BLUEPRINT Epigenome project (http://www.blueprint-epigenome.eu) and mapping to anatomical systems and organs.

## Cell types
The subset of BLUEPRINT cells included in Expression Atlas (www.ebi.ac.uk/gxa) is found in the file `cell_types_used.txt` that can be retrieved from the file `assaygroupsdetails.tsv` at `/ebi/ftp/pub/databases/microarray/data/atlas/experiments/` using the following:
```
grep 'E-MTAB-3827\|E-MTAB-3819\|E-MTAB-4754' /ebi/ftp/pub/databases/microarray/data/atlas/experiments/assaygroupsdetails.tsv | grep factor | awk -F"\t" '{print $5}' | sort | uniq
```

## Annotation of cell types to ontologies
Each of the BLUEPRINT cell types included in Expression Atlas is annotated to ontology terms using Zooma (https://www.ebi.ac.uk/spot/zooma/).

## Mapping cell types to anatomical systems and organs
Each of the BLUEPRINT cell types included in Expression Atlas has been manually mapped to organs and anatomical systems.

Here are a couple of example lines from the `blueprint_to_organs.txt` file:

|organ id|organ name|cell id|cell name|
|-|-|-|-|
|UBERON_0005057|immune organ|CL_0000863|inflammatory macrophage|
|UBERON_0000178|blood|CL_0000863|inflammatory macrophage|  
