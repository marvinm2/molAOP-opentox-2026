# Glossary and further reading

[← back to the session overview](./)

You don't need any of this to follow the session, and nobody will quiz you on the acronyms.
It's here so you can look something up mid-exercise without asking.

## The AOP vocabulary

An AOP is a chain. Something binds to a molecule, that changes a cell, the cell changes a
tissue, and eventually the animal or person is harmed. The framework gives each link a name.

| Term | What it means |
|---|---|
| AOP | Adverse Outcome Pathway. The whole chain, from first molecular contact to the harmful endpoint. |
| MIE | Molecular Initiating Event. Where the chain starts, usually a chemical interacting with a biological molecule. |
| KE | Key Event. Any measurable step along the chain. This is the unit we map to pathways in this session. |
| KER | Key Event Relationship. The link between two Key Events, carrying the evidence that one leads to the other. |
| AO | Adverse Outcome. The endpoint that regulators care about, such as liver steatosis or kidney failure. |
| Weight of evidence | How strongly the evidence supports a relationship. Judged, not calculated. |
| NAM | New Approach Methodology. Any method that gives toxicological answers without animal testing. |
| qAOP | Quantitative AOP. An AOP with a mathematical model attached, so you can predict rather than describe. |

A Key Event sits at a biological level: molecular, cellular, tissue, organ, or organism. The
Builder shows you this, and it matters, because a molecular Key Event usually has a much
crisper pathway match than an organ-level one.

## Data resources

| Term | What it means |
|---|---|
| AOP-Wiki | The public repository of AOPs. Every `KE` and `AOP` number in this session comes from there. |
| WikiPathways | Community-curated biological pathways. The `WP` identifiers. |
| GO | Gene Ontology. Structured terms for biological processes and molecular functions. |
| GO BP | The Biological Process branch of GO, the one the Builder maps Key Events to. |
| Reactome | Another curated pathway database, the third resource the Builder supports. |
| RDF / SPARQL | A way of publishing data as linked statements, and the language for querying it. AOP-Wiki has an RDF version. |
| FAIR | Findable, Accessible, Interoperable, Reusable. The properties that let a dataset be reused by someone who wasn't there when it was made. |
| DOI | A permanent identifier for a dataset or paper. What you cite. |

## Analysis terms

| Term | What it means |
|---|---|
| log2FC | Log2 fold change. How much a gene went up or down. Positive is up, and each unit is a doubling. |
| p-value | How surprising the result would be if nothing were really happening. Small means surprising. |
| FDR | False discovery rate. A p-value corrected for the fact that you tested thousands of genes at once. Use this one, not the raw p-value. |
| BH | Benjamini-Hochberg, the method used here to get from p-values to FDR. |
| Fisher's exact test | Takes your list of significantly changed genes and asks whether a pathway's genes are over-represented in it. Needs a cutoff. |
| GSEA | Gene Set Enrichment Analysis. Uses all your genes ranked by change, no cutoff, and knows the difference between up and down. |
| Gene set | The genes belonging to one pathway. What a Key Event gets when you map it. |
| Enrichment | Finding that a gene set has changed more than chance would explain. |
| BioBERT | A language model trained on biomedical text. The Builder uses it to rank candidate pathways by how similar their description is to the Key Event. |
| Confidence tier | High, medium, or low. Derived from the four questions you answer, not chosen directly. |

Fisher's and GSEA answer slightly different questions, so they disagree sometimes. That
disagreement is interesting rather than a bug, and it comes up in the questions at the end of
the exercises.

## Documentation

For the tools used in this session:

- [Builder source and README](https://github.com/marvinm2/molAOP-builder)
- [How the confidence scoring works](https://github.com/marvinm2/molAOP-builder/blob/main/docs/SCORING_CONFIG.md)
- [What is in the mapping dataset](https://github.com/marvinm2/molAOP-builder/blob/main/docs/DATASET_DOCUMENTATION.md)
- [Who decides what gets approved](https://github.com/marvinm2/molAOP-builder/blob/main/docs/GOVERNANCE.md)
- [Analyser source and README](https://github.com/marvinm2/molAOP-analyser)
- [The mapping API the Analyser reads](https://github.com/marvinm2/molAOP-analyser/blob/main/docs/KE-MAPPING-API-REFERENCE.md)

For the underlying data:

- [AOP-Wiki](https://aopwiki.org)
- [AOP-Wiki RDF and SPARQL endpoint](https://aopwiki.rdf.bigcat-bioinformatics.org)
- [WikiPathways](https://www.wikipathways.org)
- [Gene Ontology](https://geneontology.org)
- [The curated mapping dataset on Zenodo](https://doi.org/10.5281/zenodo.20184643)
