# BLUEPRINT-metadata
Ontology annotation of a subset of cell types from the [BLUEPRINT Epigenome project][1] and mapping to anatomical systems and organs.

## Cell types
The subset of BLUEPRINT cells included in [Expression Atlas][2] is found in the file `cell_types_used.txt` that was generated from the file `assaygroupsdetails.tsv` at `/ebi/ftp/pub/databases/microarray/data/atlas/experiments/` using the following:
```
grep 'E-MTAB-3827\|E-MTAB-3819\|E-MTAB-4754' /ebi/ftp/pub/databases/microarray/data/atlas/experiments/assaygroupsdetails.tsv | grep factor | awk -F"\t" '{print $5}' | sort | uniq
```

## Annotation of cell types to ontologies
Each of the BLUEPRINT cell types included in Expression Atlas is annotated to ontology terms using [Zooma][3], developed by the [Samples, Phenotypes and Ontologies Team][4] at [EMBL-EBI][5].

## Mapping cell types to anatomical systems and organs
Each of the BLUEPRINT cell types included in Expression Atlas has been manually mapped to organs and anatomical systems based on the hierarchy of [Cell Ontology][6] when possible.

Let's explain as an example the process followed to map **inflammatory macrophage** to anatomical systems in the `blueprint_to_anatomical_systems.txt` file. According to Cell Ontology, inflammatory macrophage is linked to immune system and to hematopoietic cell. Thus, is reasonable to map it to the following anatomical systems: 

|system id|system name|cell id|cell name|
|-|-|-|-|
|UBERON_0002405|immune system|CL_0000863|inflammatory macrophage|
|UBERON_0002390|hematopoietic system|CL_0000863|inflammatory macrophage|

There is no link of **inflammatory macrophage** to an organ in Cell Ontology. However, we can manually associate that cell type to the following organs in the `blueprint_to_organs.txt` file:

|organ id|organ name|cell id|cell name|
|-|-|-|-|
|UBERON_0005057|immune organ|CL_0000863|inflammatory macrophage|
|UBERON_0000178|blood|CL_0000863|inflammatory macrophage|

[1]: http://www.blueprint-epigenome.eu
[2]: https://www.ebi.ac.uk/gxa/home
[3]: https://www.ebi.ac.uk/spot/zooma/
[4]: https://www.ebi.ac.uk/about/spot-team
[5]: https://www.ebi.ac.uk/
[6]: http://purl.obolibrary.org/obo/cl.owl
