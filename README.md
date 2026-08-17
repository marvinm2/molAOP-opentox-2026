<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LearningResource",
  "name": "From Genes to Adverse Outcomes: Hands-on Molecular AOPs with Open Web Tools",
  "description": "A two-hour online session introducing the molecular Adverse Outcome Pathway workflow through two free browser-based tools: the Molecular AOP Builder, which curates Key Event to pathway mappings, and the Molecular AOP Analyser, which uses those mappings to test gene-expression data for Key Event enrichment.",
  "keywords": "Adverse Outcome Pathway, AOP, toxicology, transcriptomics, WikiPathways, Gene Ontology, enrichment analysis, NAMs",
  "audience": {
    "@type": "Audience",
    "name": "Researchers and students in toxicology and risk assessment, all levels"
  },
  "author": [
    { "@type": "Person", "name": "Marvin Martens" },
    { "@type": "Person", "name": "Sidra Adil" }
  ],
  "http://purl.org/dc/terms/conformsTo": {
    "@type": "CreativeWork",
    "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE"
  },
  "license": {
    "@type": "CreativeWork",
    "@id": "http://creativecommons.org/licenses/by/4.0/",
    "name": "CC-BY 4.0",
    "url": "https://creativecommons.org/licenses/by/4.0/"
  },
  "version": "1.0"
}
</script>

# From Genes to Adverse Outcomes

### Hands-on Molecular AOPs with Open Web Tools

**OpenTox Summer School 2026 · Wednesday 19 August 2026, 13:00–15:00 CEST · online**

Facilitators: **Dr. Marvin Martens** and **Sidra Adil**, Department of Translational
Genomics, Maastricht University.

Session page: [opentox.net](https://www.opentox.net/events/opentox-summer-school-2026/MarvinMartens&SidraAdil)

---

## What this session is about

An Adverse Outcome Pathway describes how harm unfolds: a chemical touches a molecule, that
changes a cell, and eventually something goes wrong at the level of the whole organism. Each
step is a Key Event, written down in words.

Gene expression data, meanwhile, arrives as a list of genes that went up or down. Getting from
one to the other is still awkward in practice, and that gap is what this session is about. We
use two free tools built in VHP4Safety.

| Tool | What it does | Link |
|---|---|---|
| Molecular AOP Builder | Records which pathways and Gene Ontology terms represent a Key Event. A language model proposes candidates; a curator decides. | [molaop-builder.vhp4safety.nl](https://molaop-builder.vhp4safety.nl) |
| Molecular AOP Analyser | Takes those mappings and tests your gene expression data for Key Events that have changed, then draws the result on the AOP network. | [molaop-analyser.vhp4safety.nl](https://molaop-analyser.vhp4safety.nl) |

The Builder makes the mappings and the Analyser uses them. That is the whole architecture.

Not familiar with the acronyms? The [glossary](glossary) covers them, along with links to the
documentation for both tools.

## What you need

A laptop and a browser. Nothing to install, no code to write.

The Analyser needs no login. The Builder needs a guest code, which we'll paste into the chat
when the hands-on part starts. Datasets are already in the tools, so you don't need to bring
data of your own.

## By the end you will be able to

1. Explain how molecular AOPs link gene expression data to AOP Key Events.
2. Run a Key Event enrichment analysis and read the resulting network.
3. Propose a Key Event to pathway mapping for expert review.
4. Judge how much confidence a molecular AOP result deserves.

## Programme

| Time (CEST) | Segment |
|---|---|
| 13:00 | Welcome, and an introduction to Adverse Outcome Pathways |
| 13:20 | The two tools and how they fit together. Guest code goes out in the chat |
| 13:30 | Builder: live demo |
| 13:40 | Analyser: live demo |
| 13:50 | Exercise A: propose a mapping in the Builder |
| 14:10 | Exercise B: run an enrichment in the Analyser |
| 14:30 | Live poll, discussion and questions |

The Builder exercise runs first so that a mapping you propose can be approved and then show up
in the Analyser while you are still in the room. You'll get the guest code at 13:20, so log in
during the demos rather than waiting.

## Exercises

**→ [Open the exercise sheet](exercises)**

Practice only. Nothing is handed in and nothing is marked. Work at your own pace, do as much as
interests you, and ask in the chat whenever. The sheet ends with a set of questions we'll go
through together in a live poll.

## About the facilitators

Marvin Martens and Sidra Adil are researchers in the Department of Translational Genomics
(TGX) at Maastricht University. Their work focuses on connecting Adverse Outcome Pathways
(AOPs) with transcriptomics data and developing practical approaches for mechanistically
informed, animal-free chemical safety assessment.

**Marvin** is a postdoctoral researcher with a background in biomedical sciences and
bioinformatics. His research focuses on making AOP knowledge FAIR, computable, and easier to
integrate with molecular data. He develops knowledge resources and tools such as the AOP-Wiki
RDF knowledge graph and the molAOP Builder and Analyser web applications. His work combines
semantic web technologies, transcriptomics, and computational modelling to help researchers
interpret molecular changes in the context of toxicity pathways. He contributes to initiatives
including VHP4Safety and the ELIXIR Toxicology Community.
[LinkedIn](https://www.linkedin.com/in/marvin-martens/)

**Sidra** is a PhD candidate with a background in microarray and RNA-seq data analysis. As
part of EFSA's TXG-MAP project, her research connects AOPs to transcriptomics data, allowing
gene expression measurements to be interpreted as specific steps in a toxicity pathway rather
than simply as lists of changed genes. A central challenge is that many Key Events in the
AOP-Wiki lack the ontology annotations needed to establish these connections. Much of her work
therefore involves systematically annotating Key Events across organ-specific AOP networks.
[LinkedIn](https://www.linkedin.com/in/sidra-adil-a971221a0/)

Together, Marvin and Sidra combine computational infrastructure, ontology annotation, and
transcriptomics analysis to make AOP knowledge more accessible and applicable. Their work
supports the interpretation of molecular data in a transparent biological context and advances
the use of new approach methodologies (NAMs) in chemical risk assessment.

## Resources

- [Glossary, acronyms and tool documentation](glossary)
- Source code: [`marvinm2/molAOP-builder`](https://github.com/marvinm2/molAOP-builder) ·
  [`marvinm2/molAOP-analyser`](https://github.com/marvinm2/molAOP-analyser)
- Curated mapping dataset on Zenodo: [`10.5281/zenodo.20184643`](https://doi.org/10.5281/zenodo.20184643) (CC0)
- Builder software: [`10.5281/zenodo.21914244`](https://doi.org/10.5281/zenodo.21914244) ·
  Analyser software: [`10.5281/zenodo.21914317`](https://doi.org/10.5281/zenodo.21914317)
- Public REST API for KE→pathway mappings, used by the Analyser and open to anyone:
  `https://molaop-builder.vhp4safety.nl/api/v1/mappings`

## Licence

Workshop materials are CC-BY 4.0. The curated mapping dataset is CC0, except AOP-Wiki Key
Event titles which are CC BY-SA 4.0.
