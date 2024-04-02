# Genome Annotation
# **Prokaryotic**

## Lecture

<br>

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTERGc6gJyJeGylr6xzXvioMFixfI6x9XIT8QHqC8XIq8cP3KHe6PUuumbMrunSCVlbFhFJaVh2wvMh/embed?start=false&loop=false&delayms=3000" frameborder="0" width="480" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

After you have de novo assembled your genome sequencing reads into contigs, it is useful to know what genomic features are on those contigs. The process of identifying and labelling those features is called genome annotation.

Prokka is a "wrapper"; it collects together several pieces of software (from various authors), and so avoids "re-inventing the wheel".

Prokka finds and annotates features (both protein coding regions and RNA genes, i.e. tRNA, rRNA) present on on a sequence. Prokka uses a two-step process for the annotation of protein coding regions: first, protein coding regions on the genome are identified using [Prodigal](http://compbio.ornl.gov/prodigal/); second, the function of the encoded protein is predicted by similarity to proteins in one of many protein or protein domain databases. Prokka is a software tool that can be used to annotate bacterial, archaeal and viral genomes quickly, generating standard output files in GenBank, EMBL and gff formats. More information about Prokka can be found [here](https://github.com/tseemann/prokka).

## Generating a prokkaryote annotation

Prokka Tutorial [Here](https://training.galaxyproject.org/training-material/topics/genome-annotation/tutorials/annotation-with-prokka/tutorial.html)

* The GFF and GBK files contain all of the information about the features annotated (in different formats.)
* The .txt file contains a summary of the number of features annotated.
* The .faa file contains the protein sequences of the genes annotated.
* The .ffn file contains the nucleotide sequences of the genes annotated.

### Alternate ending

Artemis is a graphical Java program to browse annotated genomes. Download it [here](http://sanger-pathogens.github.io/Artemis/Artemis/) and install it on your local computer.

Copy the .gff file produced by prokka on your computer, and open it with artemis.

You will be overwhelmed and/or confused at first, and possibly permanently. Here are some tips:

* There are 3 panels: feature map (top), sequence (middle), feature list (bottom)
* Click right-mouse-button on bottom panel and select Show products
* Zooming is done via the verrtical scroll bars in the two top panels

## Refining the prokkaryote annotation

Apollo Tutorial [Here](https://training.galaxyproject.org/training-material/topics/genome-annotation/tutorials/apollo/tutorial.html)
[Apollo practice](https://usegalaxy.eu/apollo/annotator/loadLink?loc=NC_000913.3:75609..75707&organism=5462496&tracks=2865f2fee32cb8bf6b9c6f55cad6df4e_0,028fafec2e8fc222be30ee5553614c1b_1,276298fcea47faa9ce330d02d1c5c775_0,572bd1186d72b0c9f5f9e55a70c00b74_0)

## Bonus eggNOG annotation

Let's run the same genome information with eggNOG:

```bash
emapper.py -m diamond --itype genome -i m_genetalium_improved.fasta -o annotation_eggnog_genome
```

Let's run the protein information now:

```bash
emapper.py -m diamond --itype proteins -i uniprot_mycoplasma_reviewed.faa -o annotation_eggnog_proteins
```

What do you see in the results?
What other parameter could we tweak?
