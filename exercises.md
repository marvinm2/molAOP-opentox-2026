# Exercise sheet — Molecular AOP tools

[← back to the session overview](README.md)

Everything runs in your web browser. No installation, no coding. Datasets are already
provided inside the tools, so you don't need to bring your own.

| | |
|---|---|
| **Analyser** | [molaop-analyser.vhp4safety.nl](https://molaop-analyser.vhp4safety.nl) — no login needed |
| **Builder** | [molaop-builder.vhp4safety.nl](https://molaop-builder.vhp4safety.nl) — guest code shared in the chat |

**These exercises are for practice.** Nothing is handed in and nothing is marked. Go as far
as you find interesting, skip what you don't, and ask in the chat whenever something is
unclear or doesn't behave as described.

---

## Exercise A — Enrich a dataset with the Analyser (~25 min)

**Goal:** turn a gene-expression dataset into AOP Key Event enrichment results.

No login is needed for any part of this exercise.

1. Open the **Analyser**. On the landing page, choose one of the **provided demo datasets**
   (for example a PXR agonist study).
2. Check the **auto-detected columns** — gene identifier, log2 fold change, p-value. Adjust
   them if the tool guessed wrong.
3. Pick an **AOP** to analyse against. Use the recommended one, or search for another.
4. Choose an enrichment method and run the analysis:
   - **Fisher's exact test** — threshold-based over-representation, or
   - **GSEA** — threshold-free and direction-aware.
5. Read the **results table**. Which Key Events come out significantly enriched after
   false-discovery-rate correction?
6. Explore the **interactive network**. Which Key Events light up, and how do the genes
   colour by expression? Open the **Pathway view** for one enriched Key Event.
7. **Export** a PDF report, or the gene-by-Key-Event CSV.

**Something to think about:** does the pattern of enriched Key Events tell a plausible
mechanistic story, running from the molecular initiating event toward the adverse outcome?
Or are the significant hits scattered across the network without an obvious thread?

### If you finish early — batch comparison

Use the **one-click batch demo** to compare the two PXR datasets, then open the
**comparison heatmap**. Where do the two conditions agree across Key Events, and where do
they diverge?

---

## Exercise B — Propose a mapping with the Builder (~20 min)

**Goal:** curate a Key Event → pathway mapping of the kind the Analyser depends on.

1. Open the **Builder** and click **Login**. In the login window, enter the **guest access
   code** from the chat.
2. Pick a Key Event that interests you — there are some suggestions below, but any Key Event
   in the tool is fair game.
3. Review the **suggested WikiPathways and GO terms**. They are ranked by similarity score
   from a language model, and each carries a confidence tier.
4. **Propose a mapping** for a suggestion you find biologically sensible, and add a short
   justification for why.
5. Marvin will **approve** a few proposals live so you can see them flow through to the
   Analyser.

> Your proposals are submitted under a shared guest identity rather than your own name, so
> the justification text is what makes your reasoning visible. A sentence is plenty.

### Some Key Events worth a look

Entirely optional — a starting point if you'd rather not go hunting. All of these are
genuinely **unmapped to WikiPathways** in the live database, so whatever you propose is new
curation rather than a repeat of work already done. Each already has a **GO Biological
Process** mapping, so the biology is pinned down and you are choosing the pathway that best
represents it.

| Key Event | Title | Appears in |
|---|---|---|
| `KE 54` | Up Regulation, CD36 | AOP 34, AOP 57, AOP 58 (+2) |
| `KE 462` | Up Regulation, SCD-1 | AOP 57, AOP 58, AOP 60 |
| `KE 66` | Activation, ChREBP | AOP 34, AOP 58 |
| `KE 116` | Activation, FAS | AOP 34 |
| `KE 1305` | Increase, cytosolic fatty acid | AOP 213 |
| `KE 140` | Decreased, HSD17B10 expression | AOP 36 |
| `KE 1423` | Reduced, HSD17B4 activity | AOP 232 |
| `KE 1490` | Inhibition, Fatty Acid Beta Oxidation | AOP 213 |
| `KE 1491` | Increased, Oncotic Necrosis | AOP 213 |
| `KE 1834` | Decrease, Acyl-CoA dehydrogenases | AOP 318 |
| `KE 2199` | Increased, Expression of LXR activated genes | AOP 518 |

If several people land on the same Key Event, that's fine — you'll simply see how differently
two people can read the same suggestion list, which is worth discussing in itself.

### If you finish early — the gut–liver axis (AOP 642)

These Key Events, from *Intestinal FXR inhibition → steatohepatitis*, have **no mapping in
either WikiPathways or GO**, so they need the full biological judgement rather than a
confirmation. Bile-acid signalling is well represented upstream, so there is good material
to find.

| Key Event | Title |
|---|---|
| `KE 1931` | Intestinal barrier, disruption |
| `KE 2422` | Ileal FGF15/FGF19 secretion, decreased |
| `KE 2424` | Hepatic CYP7A1, increased |
| `KE 2425` | Intrahepatic bile acid burden, increased |
| `KE 2426` | Hepatic BSEP (ABCB11), decreased |
| `KE 2427` | Bile acid composition in bile and intestine, altered |
| `KE 2428` | Gut derived PAMPs, increased |

> A few Key Events in these AOPs are deliberately left off both lists — disease endpoints
> like *Increase, Liver steatosis*, and very general events like *Activation, MAPK*. They
> are hard to map well and tend to produce low-confidence mappings. That is a real lesson
> about the method, but a frustrating first exercise.

**Seeing it connect:** once a mapping is approved it becomes available to the Analyser, so an
enrichment re-run can pick up the new Key Event → pathway link. Mappings are cached for about
an hour, so the facilitators will demonstrate this rather than have everyone wait.

**Something to think about:** what makes a mapping trustworthy? How would you weigh a
high-scoring suggestion from the model against your own reading of the biology?

---

## Two things that surprise people

- **Your confidence choice may change.** The Builder derives the confidence tier from your
  four assessment answers rather than taking the tier you picked at face value, so a
  submission asking for "low" can be stored as "medium". That is the scoring working as
  intended, not a bug.
- **Mappings are stored per Key Event, not per AOP.** A Key Event that appears in five AOPs
  is mapped once, and that mapping is inherited everywhere it appears. It is why curation
  effort compounds across the AOP network.

## Wrap-up resources

- Source code: [`marvinm2/molAOP-builder`](https://github.com/marvinm2/molAOP-builder) ·
  [`marvinm2/molAOP-analyser`](https://github.com/marvinm2/molAOP-analyser)
- Curated mapping dataset on Zenodo: [`10.5281/zenodo.20184643`](https://doi.org/10.5281/zenodo.20184643)
- Public REST API: `https://molaop-builder.vhp4safety.nl/api/v1/mappings`
