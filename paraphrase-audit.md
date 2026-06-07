# Paraphrase Proximity Audit

Audit of cited passages in `Chapters/` against the verbatim source excerpts in
`Sources/`, flagging "paraphrases" that stay close enough to the original to
read as unmarked quotes.

**Scope note:** Several files in `Sources/` (especially `06-related-work.tex`)
contain the author's own draft summaries, not verbatim source quotes. Chapter
text matching those drafts is NOT flagged — only text tracking an actual quoted
excerpt. Implementation, Results, and Conclusion chapters are the author's own
technical writing (citing only tools/libraries) and have no proximity problems.

**Status legend:** ✅ resolved · ⚠️ open · ◻️ borderline/low

Last updated after the author's SECOND revision pass.

---

## Current status at a glance

- **Tier 1 (7 items):** all resolved. ✅
- **Tier 2 (13 items):** 8, 9, 10, 11, 12, 14, 15, 17, 18, 22 resolved; **13, 16, 19, 20** still open/borderline.
- **Tier 3 (4 items):** 21 resolved; **23, 24** still open; (item 24 fixed in related-work but still open in Discussion).

### Remaining to address
- **⚠️ 13** — refinement-over-time sentence (`05-feedback.tex:6-8`) — unchanged.
- **⚠️ 20** — AutoML definition (`06-related-work-existing-tools.tex:79-80`) — unchanged.
- **⚠️ 23** — cosine value range (`04-semantic-...:48-51`) — now mirrors the full enumeration; got closer.
- **⚠️ 24** — "sparse, high-level summaries of a paper" (`08Discussion.tex:104-105`) — fixed in related-work, still present in Discussion.
- **◻️ 16** — LSTM "stored, read, and …" triplet (`01-machine-learning.tex:329-331`) — one word swapped (written→updated).
- **◻️ 19** — "a point in a high-dimensional space" (`04-semantic-...:17-18`) — opener removed, phrase still echoes.

---

## TIER 1 — Effectively unmarked quotes — ALL RESOLVED ✅

### 1. ✅ Cold start — `05-feedback.tex:28-31`
- Source: bobadilla2013. Was: "occurs when it is not possible to make reliable recommendations due to an initial lack of ratings" (15-word verbatim).
- Now: "arises when a system cannot yet recommend reliably because too few ratings have been gathered". Resolved.

### 2. ✅ Enough ratings — `05-feedback.tex:36-38`
- Source: ricci2010 (Ch.3). Was: "Enough ratings have to be collected before … understand user preferences and provide … recommendations".
- Now: "the system needs a baseline of ratings before it can model a user well enough to recommend reliably". Resolved.

### 3. ✅ Sparse data problem — `05-feedback.tex:13-16`
- Source: murphy2012 (Ch.3.3). Was: "frequently occurs when estimating counts from small amounts of data" (9-word verbatim).
- Now: "which arises whenever an estimate must be drawn from only a handful of observations". Resolved.

### 4. ✅ Posterior compromise — `05-feedback.tex:19-21`
- Source: murphy2012. Was: "the posterior is a compromise between what … previously believed and what the data".
- Now: "The resulting estimate balances the prior assumption against the evidence in the observed ratings". Resolved.

### 5. ✅ 10,000 sentences — `04-semantic-retrieval-literature-based-knowledge.tex:77-80`
- Source: reimers2019. Was: "Finding the most similar pair in a collection of 10,000 sentences … 50 million inference computations".
- Now: "For 10,000 sentences, identifying the closest pair takes on the order of 50 million forward passes through BERT". Resolved (only bare facts remain).

### 6. ✅ Overwhelmed prior — `05-feedback.tex:22-24`
- Source: murphy2012. Was: "since the data has overwhelmed the prior" (7-word verbatim).
- Now: "because the volume of observations now outweighs the prior". Resolved.

### 7. ✅ Value function / policy — `01-machine-learning.tex:56-58`
- Source: sewak2019. Was: "from which the policy is derived either explicitly or implicitly" (9-word verbatim).
- Now: "learn a value function first and obtain the policy from it, either directly or as an implicit consequence …". Resolved.

---

## TIER 2 — Distinctive phrase / structure

### 8. ✅ Neural networks definition — `01-machine-learning.tex:264-266`
- Source: shrestha2019. Was: "consisting of processing units organised in input, hidden, and output layers" (8-word verbatim) + "inspired by … the structure of the … brain".
- Now: "whose design takes after the way the human brain is built, with processing units arranged across an input layer, one or more hidden layers, and an output layer". Resolved.

### 9. ✅ Classification definition — `01-machine-learning.tex:28-29`
- Source: bishop2006. Was: "one of a finite number of discrete categories" (7-word verbatim).
- Now: "assigns an input to one of a fixed set of discrete classes". Resolved.

### 10. ✅ Ontology common vocabulary — `03-ontologies-knowledge-representation.tex:33-35`
- Source: noy2001. Was: "an ontology defines a common vocabulary for … machine-interpretable definitions of … basic concepts … and … relations among them".
- Now: "an ontology gives a domain a shared set of terms, together with definitions of its basic concepts and their relations". Resolved (remaining "definitions of basic concepts and relations" is generic).

### 11. ✅ New community problem — `05-feedback.tex:32-35`
- Source: bobadilla2013. Was: "refers to the difficulty … obtaining, a sufficient amount of … data".
- Now: "refers to the trouble a freshly launched system has in accumulating enough rating data to recommend well". Resolved.

### 12. ✅ Explicit/implicit feedback — `05-feedback.tex:3-4`
- Source: bobadilla2013. Was: "explicitly … ratings, or implicitly by monitoring users' behaviour".
- Now: "Feedback from users can be captured explicitly through numerical ratings" — the "implicitly by monitoring user behaviour" clause was removed. Resolved.

### 13. ⚠️ Refinement over time — `05-feedback.tex:6-8`  (UNCHANGED — still open)
- Source: ricci2010 (Ch.1).
- My text: "so that the longer users engage with the system, the more the output can be refined to match their preferences"
- Source text: "the longer the user interacts with the site, the more refined her user model becomes [...] the more the recommender output can be effectively customized to match the user's preferences."
- Overlap: "the longer … the more … output … to match … preferences"
- Note: The "the longer X … the more … output … to match … preferences" construction still mirrors the source. Consider recasting, e.g. "ratings collected over repeated use let the system tailor results to each user."

### 14. ✅ Dimensionality reduction — `01-machine-learning.tex:40-42`
- Source: sarker2021. Was: "better human interpretation[s] … lower computational cost[s]".
- Now: "so the data becomes easier for people to interpret and cheaper to process". Resolved.

### 15. ✅ Clustering definition — `01-machine-learning.tex:37-38`
- Source: sarker2021. Was: "more similar to each other than … in other groups".
- Now: "the members of one group resemble each other more closely than they resemble the members of other groups". Resolved.

### 16. ◻️ LSTM gates — `01-machine-learning.tex:329-331`  (improved, borderline)
- Source: shrestha2019.
- My text: "memory cells together with gates that decide which information is stored, read, and updated"
- Source text: "These gates control what is stored, read and written on the cell."
- Overlap: "stored, read, and …" (the gate-operation triplet, with "written→updated")
- Note: Only the final word was swapped (written→updated). The "is stored, read, and …" list still echoes the source. Low severity (near-standard gate description), but technically the "trivial swap" pattern.

### 17. ✅ CNN local connections — `01-machine-learning.tex:300-302`
- Source: pouyanfar2018. Was: "local connections and shared weights" + "which makes the network faster … to train".
- Now: "CNNs rely on local connections and weight sharing, which keeps the parameter count low and shortens training time". Resolved (remaining "local connections" is standard terminology).

### 18. ✅ Dense retrieval — `04-semantic-retrieval-literature-based-knowledge.tex:129-131`
- Source: jurafsky_martin2026 (11.1). Was: "documents and queries … embeddings, computed from language models".
- Now: "mapping documents and queries to embeddings produced by a language model, instead of vectors of word counts". Resolved (verbs changed; remaining overlap is generic).

### 19. ◻️ Vector semantics / embedding — `04-semantic-retrieval-literature-based-knowledge.tex:17-18`  (improved, borderline)
- Source: jurafsky_martin2026 (p.116).
- My text: "Text can be represented as a numerical vector, a point in a high-dimensional space referred to as the embedding space"
- Source text: "In vector semantics, a word is modeled as a vector—a point in high-dimensional space, also called an embedding."
- Overlap: "a point in a high-dimensional space … embedding"
- Note: The "In vector semantics" opener was removed (good), but "a point in a high-dimensional space" still echoes the source. Fairly standard description; low severity.

### 20. ⚠️ AutoML definition — `06-related-work-existing-tools.tex:79-80`  (UNCHANGED — still open)
- Source: waring2020.
- My text: "AutoML, which automatically selects, composes, and parametrises models for a given task or dataset"
- Source text: "Automated machine learning (AutoML) … automatically select, compose, and parametrize machine learning models, so as to achieve optimal performance on a given task and/or dataset."
- Overlap: "automatically select[s], compose[s], and parametri[s]e … models … on/for a given task … dataset"
- Note: The triplet verb list and "on/for a given task … dataset" are the source's, only conjugated. Recast, e.g. "AutoML automates model choice, assembly, and configuration for a dataset."

### 21. ✅ Explicit (definition gloss) — `03-ontologies-knowledge-representation.tex:28-29`
- Source: studer1998. Was: "the concepts used … and the constraints on their use are … defined" (near-verbatim gloss).
- Now: "the concepts and the constraints on how they may be used are defined directly rather than left implicit". Resolved.

### 22. ✅ Minimal commitment — `03-ontologies-knowledge-representation.tex:50-52`
- Source: gruber1995. Was: "make as few claims … about the world".
- Now: "committing to as little about the modelled world as the task allows". Resolved (the "few claims about the world" phrase is gone; "minimal ontological commitment" is a defined term).

---

## TIER 3 — Borderline / lower severity

### 23. ⚠️ Cosine value range — `04-semantic-retrieval-literature-based-knowledge.tex:48-51`  (GOT CLOSER)
- Source: jurafsky_martin2026 (5.4).
- My text: "The result is 1 when the vectors point in the same direction, indicating maximum similarity, falls to 0 when they are orthogonal and share no similarity, and reaches −1 when they point in opposite directions"
- Source text: "The cosine value ranges from 1 for vectors pointing in the same direction, through 0 for orthogonal vectors, to -1 for vectors pointing in opposite directions."
- Overlap: "vectors point in the same direction" / "0 … orthogonal" / "point in opposite directions" — and the same 1→0→−1 enumeration order.
- Note: Now mirrors the full source enumeration (it added the −1 case). "point(ing) in the same/opposite direction" is near-verbatim. Standard math description, but the structure tracks the source closely. Consider reordering or stating it as a range.

### 24. ⚠️ Abstracts as sparse summaries — `08Discussion.tex:104-105`  (fixed in related-work, STILL OPEN here)
- Source: park2026 (`Sources/Discussion/discussion.tex`).
- My text (Discussion): "abstracts offer only sparse, high-level summaries of a paper"
- Source text: "abstracts offer only sparse and highlevel summaries"
- Overlap: "abstracts offer only sparse … high-level summaries" (6 words)
- Note: The related-work occurrence was reworded ("an abstract captures only a brief, surface-level view of a paper" — resolved). The Discussion occurrence still uses the source phrase verbatim. Reword to match, or quote it.

---

## Chapters with no problems
- `03Introduction.tex`, `02-ml-in-production-product-development.tex`, `05Methodology-System-Overview.tex`,
  all `06Implementation/` sub-chapters, `07Results.tex`, `09Conclusion.tex` (empty),
  `00Abstract.tex`, and `08Discussion.tex` (except item 24).
