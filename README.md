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

---

## What this session is about

Adverse Outcome Pathways (AOPs) organise mechanistic knowledge from a molecular initiating
event, through a series of key events, to an adverse outcome. Connecting them to real
molecular measurements is still a practical bottleneck. This session walks through the
molecular AOP (mol-AOP) workflow using two free tools developed within VHP4Safety.

| Tool | What it does | Link |
|---|---|---|
| **Molecular AOP Builder** | Curates mappings between AOP Key Events and biological pathways (WikiPathways) and Gene Ontology terms, using language-model similarity scoring to suggest candidates for expert review. | [molaop-builder.vhp4safety.nl](https://molaop-builder.vhp4safety.nl) |
| **Molecular AOP Analyser** | Uses those curated mappings to test gene-expression datasets for Key Event enrichment, visualises the results as interactive AOP networks, and generates reports. | [molaop-analyser.vhp4safety.nl](https://molaop-analyser.vhp4safety.nl) |

The Builder produces the mappings; the Analyser consumes them.

## What you need

**Just a laptop and a web browser.** There is nothing to install and no code to write.

- The **Analyser needs no login at all.**
- The **Builder needs a guest access code**, which the facilitators will paste into the
  chat at the start of the hands-on part.
- **Datasets are provided inside the tools** — you do not need to bring your own data.

## By the end you will be able to

1. Explain how molecular AOPs link gene-expression data to AOP Key Events.
2. Run a Key Event enrichment analysis and interpret the resulting AOP network.
3. Curate and propose a Key Event–pathway mapping for expert review.
4. Judge the confidence and weight of evidence behind a molecular AOP result.

## Programme

| Time (CEST) | Segment |
|---|---|
| 13:00 | Introduction to AOPs and molecular AOPs |
| 13:15 | Molecular AOP Builder — live demo |
| 13:40 | Molecular AOP Analyser — live demo |
| 14:05 | Hands-on setup, guest code shared in the chat |
| 14:10 | **Exercise A** — run an enrichment in the Analyser |
| 14:35 | **Exercise B** — propose a mapping in the Builder |
| 14:55 | Wrap-up and Q&A |

## Exercises

**→ [Open the exercise sheet](exercises.md)**

The exercises are for practice and exploration — there is nothing to hand in and no
assessment. Work at your own pace, do as much as interests you, and ask in the chat at any
point.

## Resources

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
