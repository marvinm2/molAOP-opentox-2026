# Exercise sheet

[← back to the session overview](./) · [glossary and further reading](glossary)

Everything runs in your browser. Nothing to install, no code to write, and the datasets are
already inside the tools.

| | |
|---|---|
| Builder | [molaop-builder.vhp4safety.nl](https://molaop-builder.vhp4safety.nl) — use the guest code from the chat |
| Analyser | [molaop-analyser.vhp4safety.nl](https://molaop-analyser.vhp4safety.nl) — no login needed |

These are for practice. Nothing is handed in and nothing is marked, so go as far as you find
interesting and skip what you don't. If a term is unfamiliar, the [glossary](glossary) has it.
If something doesn't behave the way it's written here, say so in the chat, because that is
usually us rather than you.

Exercise A comes first because your mapping can then show up in Exercise B.

---

## Exercise A: curate a mapping in the Builder (~20 min)

A Key Event is a step in an AOP, described in words. To test it against gene expression data
you need to know which genes represent it. That is what a mapping is, and that is what you are
about to make.

1. Open the Builder, click Login, and enter the guest code from the chat.
2. Pick a Key Event that interests you. There are suggestions below, but anything in the tool
   is fair game.
3. Look at the suggested WikiPathways and GO terms. A language model ranked them by how closely
   their description matches the Key Event text. Ranking is not agreement, so read them.
4. Choose one you find biologically sensible and propose it, with a sentence saying why.
5. Marvin will approve some proposals live during the session.

Your proposal is submitted under a shared guest identity rather than your own name, so the
justification is the only place your reasoning shows up. One sentence is plenty.

### Some Key Events worth a look

Two flavours, depending on how much of a hunt you want.

#### There is a good pathway waiting to be found

For each of these, WikiPathways contains an entry that fits the Key Event closely. The work is
finding it, checking that it really represents the biology, and deciding how confident you are.

| Key Event | Title | Appears in |
|---|---|---|
| `KE 264` | Activation, SREBP-1c | AOP 34 |
| `KE 715` | Activation, Constitutive androstane receptor | AOP 107 |
| `KE 941` | Activation, EGFR | AOP 148 |
| `KE 2221` | Altered Liver X receptor activity | AOP 525 |
| `KE 1424` | Reduced, fatty acid beta oxidation | AOP 232 |
| `KE 1792` | Toll-like receptor 4 activation | AOP 347 |
| `KE 1994` | Increase, Ferroptosis | AOP 615 |
| `KE 1512` | Unfolded Protein Response | AOP 260, AOP 285, AOP 464 |
| `KE 1752` | Increased Angiotensin II | AOP 319, AOP 381, AOP 384 (+1) |
| `KE 1276` | Lung fibrosis | AOP 206, AOP 319, AOP 382 (+2) |
| `KE 179` | Decrease, Fatty acid beta-oxidation | AOP 36, AOP 497, AOP 529 (+4) |
| `KE 1457` | Epithelial Mesenchymal Transition | AOP 206, AOP 241, AOP 280 (+7) |

The ones near the bottom appear in a lot of AOPs at once. Mappings are stored per Key Event,
not per AOP, so a single mapping there is inherited by every AOP the event belongs to. Curation
effort compounds.

#### Genuinely uncharted

No WikiPathways mapping and no obvious namesake either, so these need real biological
judgement. Each already has a GO Biological Process term attached, which pins down the biology
and leaves you choosing the pathway that best represents it.

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

If several people land on the same Key Event, no harm done. You will see how differently two
people read the same suggestion list, which is worth talking about on its own.

### Harder still: the gut-liver axis (AOP 642)

These come from *Intestinal FXR inhibition leading to steatohepatitis* and have no mapping in
WikiPathways or GO. Bile acid signalling is well covered upstream, so there is material to
find.

| Key Event | Title |
|---|---|
| `KE 1931` | Intestinal barrier, disruption |
| `KE 2422` | Ileal FGF15/FGF19 secretion, decreased |
| `KE 2424` | Hepatic CYP7A1, increased |
| `KE 2425` | Intrahepatic bile acid burden, increased |
| `KE 2426` | Hepatic BSEP (ABCB11), decreased |
| `KE 2427` | Bile acid composition in bile and intestine, altered |
| `KE 2428` | Gut derived PAMPs, increased |

Some Key Events in these AOPs are deliberately missing from both lists. Disease endpoints like
*Increase, Liver steatosis* and very general events like *Activation, MAPK* are hard to map
well and tend to produce weak mappings. That is a real lesson about the method, but a
frustrating first exercise.

---

## Exercise B: run an enrichment in the Analyser (~20 min)

Now use mappings like the one you just proposed. No login needed for any of this.

1. Open the Analyser and choose one of the provided demo datasets, for example a PXR agonist
   study.
2. Check the auto-detected columns: gene identifier, log2 fold change, p-value. Fix them if the
   tool guessed wrong.
3. Pick an AOP to analyse against. Use the recommended one or search for another.
4. Choose a method and run it. Fisher's exact test needs a significance cutoff and asks whether
   a pathway's genes are over-represented among your changed genes. GSEA uses your whole ranked
   list, no cutoff, and knows up from down.
5. Read the results table. Which Key Events are significant after FDR correction?
6. Open the network. Which Key Events light up, and how do genes colour by expression? Try the
   Pathway view on one enriched Key Event.
7. Export a PDF report, or the gene-by-Key-Event CSV.

### If you finish early

Run the one-click batch demo comparing the two PXR datasets and open the comparison heatmap.
Where do the two conditions agree across Key Events, and where do they part ways?

Also worth trying: run the same dataset and AOP with Fisher's and then with GSEA, and see
whether you get the same Key Events.

---

## Questions to bring back

We'll go through these together after the hands-on part, so jot down your answers as you go.
No wrong answers, and disagreement is the interesting outcome.

### About the mapping you made

1. Which Key Event did you pick, and which pathway did you map it to?
2. Was your pathway in the top three suggestions, or did you have to go looking?
3. Did you agree with the model's top-ranked suggestion? Fully, partly, or not at all?
4. What confidence tier did you end up with, and did the tool give you the tier you expected?
5. Was there a suggestion that scored well but was biologically wrong? What gave it away?

### About the enrichment

6. Which method gave you more significant Key Events, Fisher's or GSEA?
7. Did the significant Key Events form a believable chain from the molecular initiating event
   towards the adverse outcome, or were they scattered?
8. Did any Key Event come out significant that you think is a false positive? Why?
9. Were there Key Events with no result at all? What would that tell you?

### The judgement calls

10. What would you need to know about a mapping before trusting it in a regulatory assessment?
11. A model ranked a pathway first and your reading of the biology says otherwise. Who wins,
    and how should the tool record that disagreement?
12. Is a Key Event that appears in twelve AOPs more valuable to map than one appearing in one?
    Argue either way.

---

## Afterwards

- Source code: [`marvinm2/molAOP-builder`](https://github.com/marvinm2/molAOP-builder) and
  [`marvinm2/molAOP-analyser`](https://github.com/marvinm2/molAOP-analyser)
- [Glossary and documentation links](glossary)
- The curated mapping dataset on Zenodo: [`10.5281/zenodo.20184643`](https://doi.org/10.5281/zenodo.20184643)
- Public API, open to anyone: `https://molaop-builder.vhp4safety.nl/api/v1/mappings`
