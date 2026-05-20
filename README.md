# Neuropeptide-Sequence-Analysis
This project covers a bioinformatics pipeline that explores the conservation of the D2 dopamine receptor across five vertebrate species. The motivation for this project was becoming familiar with bioinformatics pipeline building and gaining more knowledge on the computational tools often used in this domain. Ultimately, this project is a tangible preparation for a Masters programme in Bioinformatics and Systems Biology
## Research Question

**How similar are the D2 dopamine receptor protein sequences of 5 vertebrates species with different evolutionary trajectories? What does the similarity tell us about this receptor's pharmaceutic targeting?**

Through my neuroscience coursework, dopamine, a highly relevant neurotransmitter  has often come up as a key actor in the development, circuitry and treatment of neurological and neuropsychological disorders. Specifically, medication for diseases such as Parkinson's and schizophrenia mainly target the dopamine receptor D2 (DRD2) making it an important target for sequence analysis. That is because if DRD2's amino acid sequence has remained largely unchanged over hundreds of millions of years of evolution it can be strong evidence that its structure is essential, and any mutation can likely lead to harmful circumstances. Therefore, this projects uses sequence alignnment and phylogenetic analysis to test this idea across five species named below.

Moreover, the DRD2 is involved in the (disrupted) dopamine circuity of more disorders such as Attention-Deficit/Hyperactivity Disorder (ADHD), for which I gained a genuine interest while working on a project investigating the mechanism of action of the two of its most commonly prescribed medications: Methylphenidate and Amphethamines.

## Data Used
The data used for this project include 5 protein sequences of commonly studied vertabrate species downloaded from the NCBI RefSeq using Biopytho's entrez module. Accession for each species is also included for transparency.
1. Homo sapiens (human) - NP_000787.1
2. Mus musculus (mouse) - NP_034191.2
3. Rattus norveicus (rat) - NP_036867.1
4. Gallus gallus (chicken) - NP_001001461.1
5. Danio rerio (Zebrafish) - NP_922917.1

I chose these species since they have a wide evolutionary range since  mammals (which share a common ancestor around 90 million years ago) and fish and birds (which diverged from the mammalian lineage around 400 million years ago) are included. This wide evolutionary range is important for looking at sequence conservaion across a more complex evolutionary history, and not just closely related species.

## Methods
The pipeline is divided in three steps:
1. Sequence fetching: Using Biopython to pull five protein sequences from the NCBI and save them to a fasta file sequences.fasta
2. Multiple sequence alignment: Using the alignment tool MUSCLE v3.8.31 to align all five sequences and assing the output to another fasta file aligned.fasta
3. Visualisation: Using Biopython Phylo to build a phylogenetic tree using the neighbour-joining algorithm tree.nwk; and using matplotlib and seaborn to produce the conservation barchar and pairwise identity matrix

**Tools**: Python 3.14, Biopython, MUSCLE v3.8.31, matplotlib, seaborn, pandas, Jupyter Notebook.
All code can be found in neuropeptide_analysis.ipynb

## Results
<img width="869" height="623" alt="conservation_heatmap_pairwise" src="https://github.com/user-attachments/assets/8032905b-dc24-4188-a92a-df28f181b996" />

The pairwise identity matrix has revealed the following findings:
- The human-rat (20%) and Human-mouse (17%) pairs showcase surprisingly low idenity scores. 
- The human-zebrafish (54%) pair showcases the highest indentity score.
- The chicken shows the lowest identity across all other species (ranging 12-15%) which may suggest a lineage specific divergence in this receptor.

<img width="2085" height="527" alt="conservation_heatmap_barchart" src="https://github.com/user-attachments/assets/3ae63463-a80e-4832-adec-39d0816e877f" />

The conservation barchart shows 10 windows of amino acids compared to the 80% conservation threshold. The green bars above the threshold belong to the tranmembrance helices while the red and orange regions between them are the loop regions (which are less constrained structurally and likely evolve faster) 

## Discussion
The human-rat (20%) and Human-mouse (17%) pairs' low score is an unexpected finding of this project. However, this might be due to the fact that mostly the critical parts of the receptor are well conserved and cluster tightly in the transmembrane domains. 
Moreover, the high human-zebrafish (54%) indentity score is the most interesting finding. While intially it seemed like an error (since zebrafish are fish and not mammals), this finding might actually point to the fact that the DRD2 of zebrafish are highly conserved due to their high importance to its locomotion and reward circuits. It can also be a result of the fact that this Danio rerio sequence is the full-lenght isoform which has more of the ancestral receptor structure

The hypothesis that DRD2 is functionally constrained is supported by the overall pattern. It entails that the transmembrane core, the place where antipsychothics bind is the most conserved part across all five species. This also confirms why rodent models are often used to develop drugs for this receptor: they translate well since the binding space is largely the same.

### Future Directions
If I had more time I would also want to see whether the green regions of the heatmap correspond directly to the binding pocket or the structural core of the protein which would further clarify the results. I would also like to run the same pipeline using more species to create a more comprehensive phylogenetic tree.

## About this project
This is the first project I built in the field of bioinformatics while preparing for the application to a Masters Programme in Bioinformatics and Systems Biology. I used an AI chatbot as a learning assistant throughout. I did not use it as a code generator, but rather as an aid throughout code writing since this is a skill I am currently improving. However, every cell in the notebook is a step I worked through and can explain. I this process was important for my goal of producing a project that is meaningful while learning about the field and common pipelines used in bioinformatics. AI is a great tool for learning, however transparency about its usage is essential and it is something I genuienly care about.
