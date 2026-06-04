# Paraphrase Proximity Audit

Audit of cited passages in `Chapters/` against the verbatim source excerpts in
`Sources/`, flagging "paraphrases" that stay close enough to the original to
read as unmarked quotes.

**Scope note:** Several files in `Sources/` (especially `06-related-work.tex`)
contain the author's own draft summaries, not verbatim source quotes. Chapter
text matching those drafts is NOT flagged — only text tracking an actual quoted
excerpt. Implementation, Results, and Conclusion chapters are the author's own
technical writing (citing only tools/libraries) and have no proximity problems.

**Status legend:** ✅ resolved (re-checked after edits) · ⚠️ open · ◻️ borderline/low

Last updated after the author's first revision pass (Tier 1 + item 11 reworked).

---

## TIER 1 — Effectively unmarked quotes (long verbatim runs) — ALL RESOLVED ✅

### 1. ✅ Cold start — `Chapters/04Background/sub-chapters/05-feedback.tex:29-31`
- Source: `Sources/Background/05-feedback.tex` (bobadilla2013)
- Source text: "The cold-start problem [...] occurs when it is not possible to make reliable recommendations due to an initial lack of ratings."
- Original overlap: "occurs when it is not possible to make reliable recommendations due to an initial lack of ratings" (15 words verbatim)
- Revised text: "The cold start problem arises when a system cannot yet recommend reliably because too few ratings have been gathered"
- Result: Restructured; no shared run remains.

### 2. ✅ Enough ratings — `05-feedback.tex:37-38`
- Source: `Sources/Background/05-feedback.tex` (ricci2010, Ch.3)
- Source text: "Enough ratings have to be collected before a content-based recommender system can really understand user preferences and provide accurate recommendations."
- Original overlap: "Enough ratings have to be collected before … understand user preferences and provide … recommendations" (~14 words)
- Revised text: "the system needs a baseline of ratings before it can model a user well enough to recommend reliably"
- Result: Reworded; "model a user" replaces "understand user preferences", no shared run.

### 3. ✅ Sparse data problem — `05-feedback.tex:14-16`
- Source: `Sources/Background/05-feedback.tex` (murphy2012, Ch.3.3)
- Source text: "the zero count problem or the sparse data problem, and frequently occurs when estimating counts from small amounts of data"
- Original overlap: "frequently occurs when estimating counts from small amounts of data" (9 words verbatim)
- Revised text: "This is a form of the sparse data problem, which arises whenever an estimate must be drawn from only a handful of observations"
- Result: Reworded; "sparse data problem" remains as a defined term (acceptable).

### 4. ✅ Posterior compromise — `05-feedback.tex:20-22`
- Source: `Sources/Background/05-feedback.tex` (murphy2012, Ch.3.3)
- Source text: "the posterior is a compromise between what we previously believed and what the data is telling us"
- Original overlap: "the posterior is a compromise between what … previously believed and what the data" (~12 words)
- Revised text: "The resulting estimate balances the prior assumption against the evidence in the observed ratings"
- Result: Fully reworded.

### 5. ✅ 10,000 sentences — `04-semantic-retrieval-literature-based-knowledge.tex:77-80`
- Source: `Sources/Background/04-text-embeddings-semantic-similarity.tex` (reimers2019)
- Source text: "Finding the most similar pair in a collection of 10,000 sentences requires about 50 million inference computations (~65 hours) with BERT."
- Original overlap: "Finding the most similar pair in a collection of 10,000 sentences … 50 million inference computations" (~11 words)
- Revised text: "Because every candidate pair must be processed jointly, the cost grows with the size of the collection. For 10,000 sentences, identifying the closest pair takes on the order of 50 million forward passes through BERT."
- Result: Restructured; only the bare facts (10,000; 50 million) remain, which are unavoidable.

### 6. ✅ Overwhelmed prior — `05-feedback.tex:23-25`
- Source: `Sources/Background/05-feedback.tex` (murphy2012, Ch.3.3)
- Source text: "since the data has overwhelmed the prior"
- Original overlap: "since the data has overwhelmed the prior" (7 words verbatim)
- Revised text: "because the volume of observations now outweighs the prior"
- Result: Reworded (overwhelmed→outweighs, data→volume of observations).

### 7. ✅ Value function / policy — `01-machine-learning.tex:56-58`
- Source: `Sources/Background/01-machine-learning/machine-learning.tex` (sewak2019)
- Source text: "we learn a 'value function' from which the 'policy' is derived either explicitly or implicitly. Whereas in the policy-based approaches there is no need to learn or derive the value function, and we learn the 'policy' directly."
- Original overlap: "from which the policy is derived either explicitly or implicitly" (9 words verbatim)
- Revised text: "Value-based methods learn a value function first and obtain the policy from it, either directly or as an implicit consequence. Policy-based methods skip the value function and optimise the policy on its own"
- Result: Reworded; verbatim clause gone.

---

## TIER 2 — Distinctive phrase reused / structure closely followed

### 8. ⚠️ Neural networks definition — `01-machine-learning.tex:253-255`
- Source: `Sources/Background/01-machine-learning/ml-methods.tex` (shrestha2019)
- My text: "Neural networks are machine learning models inspired by the structure of the human brain, consisting of processing units organised in input, hidden, and output layers"
- Source text: "Neural Network is a machine learning technique that is inspired by … the structure of the brain. It consists of processing units organized in input, hidden and output layers."
- Overlap: "processing units organi[s]ed in input, hidden … output layers" (8 words) + "machine learning … inspired by … the structure of the … brain"
- Note: Two consecutive source clauses reproduced with near-identical wording.

### 9. ⚠️ Classification definition — `01-machine-learning.tex:27-30`
- Source: `Sources/Background/01-machine-learning/machine-learning.tex` (bishop2006)
- My text: "an input is assigned to one of a finite number of discrete categories, whereas in regression a continuous numerical value is predicted"
- Source text: "assign each input vector to one of a finite number of discrete categories, are called classification problems. If the desired output consists of one or more continuous variables, then the task is called regression."
- Overlap: "one of a finite number of discrete categories" (7 words verbatim)
- Note: Borderline (near-canonical definition), but the 7-word run is exact.

### 10. ⚠️ Ontology common vocabulary — `03-ontologies-knowledge-representation.tex:33-36`
- Source: `Sources/Background/03-ontologies.tex` (noy2001)
- My text: "an ontology defines a common vocabulary for a domain, including machine-interpretable definitions of its basic concepts and the relations among them"
- Source text: "An ontology defines a common vocabulary for researchers who need to share information in a domain. It includes machine-interpretable definitions of basic concepts in the domain and relations among them."
- Overlap: "an ontology defines a common vocabulary for … domain … machine-interpretable definitions of … basic concepts … and … relations among them"
- Note: Two source clauses spliced; almost every content word is the source's.

### 11. ✅ New community problem — `05-feedback.tex:33-35`  (FIXED in revision pass)
- Source: `Sources/Background/05-feedback.tex` (bobadilla2013)
- Source text: "The new community problem [...] refers to the difficulty, when starting up a RS, in obtaining, a sufficient amount of data (ratings) for making reliable recommendations."
- Original overlap: "refers to the difficulty … obtaining, a sufficient amount of … data"
- Revised text: "the new community problem, which refers to the trouble a freshly launched system has in accumulating enough rating data to recommend well"
- Result: Reworded; "difficulty … obtaining a sufficient amount of data" no longer present.

### 12. ⚠️ Explicit/implicit feedback — `05-feedback.tex:3-4`
- Source: `Sources/Background/05-feedback.tex` (bobadilla2013)
- My text: "User preferences can be captured explicitly through numerical ratings, or implicitly by monitoring user behaviour"
- Source text: "The information can be acquired explicitly (typically by collecting users' ratings) or implicitly [...] (typically by monitoring users' behavior)"
- Overlap: "explicitly … ratings, or implicitly by monitoring users' behavio[u]r"
- Note: The "explicitly … or implicitly by monitoring users' behaviour" frame is the source's, with only "users'→user". Still open.

### 13. ⚠️ Refinement over time — `05-feedback.tex:7-9`
- Source: `Sources/Background/05-feedback.tex` (ricci2010, Ch.1)
- My text: "the longer users engage with the system, the more the output can be refined to match their preferences"
- Source text: "the longer the user interacts with the site, the more refined her user model becomes [...] the more the recommender output can be effectively customized to match the user's preferences."
- Overlap: "the longer … the more … output can be … to match … preferences"
- Note: "the longer X … the more … to match … preferences" construction copied; verbs swapped but the shape is the source's. Still open.

### 14. ⚠️ Dimensionality reduction — `01-machine-learning.tex:40-42`
- Source: `Sources/Background/01-machine-learning/machine-learning.tex` (sarker2021)
- My text: "Dimensionality reduction simplifies data by reducing the number of features, leading to better human interpretation and lower computational cost"
- Source text: "Dimensionality reduction … leads to better human interpretations, lower computational costs, and avoids overfitting … by simplifying models."
- Overlap: "better human interpretation[s] … lower computational cost[s]"
- Note: Distinctive paired phrase reused with only plural→singular changes.

### 15. ⚠️ Clustering definition — `01-machine-learning.tex:37-39`
- Source: `Sources/Background/01-machine-learning/machine-learning.tex` (sarker2021)
- My text: "Clustering groups data points such that objects within the same group are more similar to each other than to those in other groups"
- Source text: "objects in the same category, called a cluster, are in some sense more similar to each other than objects in other groups."
- Overlap: "more similar to each other than … in other groups"
- Note: Defining phrase reproduced almost intact.

### 16. ⚠️ LSTM gates — `01-machine-learning.tex:320-322`
- Source: `Sources/Background/01-machine-learning/ml-methods.tex` (shrestha2019)
- My text: "introducing memory cells and gating mechanisms that control what information is stored, read, and written"
- Source text: "regulated by input, forget and output gates. These gates control what is stored, read and written on the cell."
- Overlap: "control what … is stored, read … and written"
- Note: "stored, read and written" reproduced verbatim.

### 17. ⚠️ CNN local connections — `01-machine-learning.tex:291-294`
- Source: `Sources/Background/01-machine-learning/ml-methods.tex` (pouyanfar2018)
- My text: "CNNs use local connections and shared weights, which reduces the number of parameters and makes the network faster to train"
- Source text: "local connections and shared weights in the network are utilized … This process results in very fewer parameters, which makes the network faster and easier to train."
- Overlap: "local connections and shared weights" (5 words) + "which makes the network faster … to train"
- Note: Two source phrases reused; second is near-verbatim.

### 18. ⚠️ Dense retrieval — `04-semantic-retrieval-literature-based-knowledge.tex:124-128`
- Source: `Sources/Background/04-text-embeddings-semantic-similarity.tex` (jurafsky_martin2026, 11.1)
- My text: "representing documents and queries as embeddings computed from language models, rather than as word count vectors"
- Source text: "In dense retrieval, we represent documents and queries with embeddings, computed from language models."
- Overlap: "documents and queries … embeddings, computed from language models" (~7 words)
- Note: Core clause lifted with "with→as".

### 19. ⚠️ Vector semantics — `04-semantic-retrieval-literature-based-knowledge.tex:17-19`
- Source: `Sources/Background/04-text-embeddings-semantic-similarity.tex` (jurafsky_martin2026, p.116)
- My text: "In vector semantics, text is represented as a numerical vector, a point in a high-dimensional space referred to as the embedding space"
- Source text: "In vector semantics, a word is modeled as a vector—a point in high-dimensional space, also called an embedding."
- Overlap: "In vector semantics, … a point in … high-dimensional space … embedding"
- Note: Opening and the "a point in [a] high-dimensional space" phrase track the source closely.

### 20. ⚠️ AutoML definition — `06-related-work-existing-tools.tex:79-80`
- Source: `Sources/Background/01-machine-learning/selecting-ml-method-and-frameworks.tex` (waring2020)
- My text: "AutoML, which automatically selects, composes, and parametrises models for a given task or dataset"
- Source text: "Automated machine learning (AutoML) … automatically select, compose, and parametrize machine learning models, so as to achieve optimal performance on a given task and/or dataset."
- Overlap: "automatically select[s], compose[s], and parametri[s]e … models … on a given task … dataset"
- Note: The triplet verb list and "on/for a given task … dataset" are the source's, only conjugated.

---

## TIER 3 — Borderline / lower severity

### 21. ◻️ Explicit (definition gloss) — `03-ontologies-knowledge-representation.tex:26-31`
- Source: `Sources/Background/03-ontologies.tex` (studer1998)
- My text: "Explicit means that the concepts used and the constraints on their use are defined explicitly."
- Source text: "'Explicit' means that the type of concepts used, and the constraints on their use are explicitly defined."
- Overlap: "the concepts used … and the constraints on their use are … defined"
- Note: Unpacks a quoted definition (partly unavoidable), but the gloss is near-verbatim ("explicitly defined→defined explicitly").

### 22. ◻️ Minimal commitment — `03-ontologies-knowledge-representation.tex:50-53`
- Source: `Sources/Background/03-ontologies.tex` (gruber1995)
- My text: "it should make as few claims about the world as necessary"
- Source text: "An ontology should make as few claims as possible about the world being modeled."
- Overlap: "make as few claims … about the world"
- Note: "minimal ontological commitment" is a defined term (fine); the "make as few claims … about the world" phrase is the borrowed bit.

### 23. ◻️ Cosine range — `04-semantic-retrieval-literature-based-knowledge.tex:48-50`
- Source: `Sources/Background/04-text-embeddings-semantic-similarity.tex` (jurafsky_martin2026, 5.4)
- My text: "The result ranges from 1, indicating identical direction and maximum similarity, to 0 for orthogonal vectors with no similarity"
- Source text: "The cosine value ranges from 1 for vectors pointing in the same direction, through 0 for orthogonal vectors, to -1 …"
- Overlap: "ranges from 1 … 0 for orthogonal vectors"
- Note: Mostly reworded; "0 for orthogonal vectors" is the only shared run (largely unavoidable technical phrasing).

### 24. ◻️ Abstracts are sparse summaries — `06-related-work-existing-tools.tex:180` AND `08Discussion.tex:176`
- Source: `Sources/Discussion/discussion.tex` (park2026)
- My text: "abstracts offer only sparse, high-level summaries of a paper"
- Source text: "abstracts offer only sparse and highlevel summaries"
- Overlap: "abstracts offer only sparse … high-level summaries" (6 words)
- Note: Short but distinctive verbatim phrase; appears in two chapters. Quote it or reword (e.g. "give only brief, surface-level overviews").

---

## Chapters with no problems
- `03Introduction.tex` — genuinely reworded.
- `04Background/sub-chapters/02-ml-in-production-product-development.tex` — clean synthesis.
- `05Methodology-System-Overview.tex` — DSR passages reworded.
- All `06Implementation/` sub-chapters — own technical writing; model/tool citations paraphrased at a safe distance.
- `07Results.tex`, `09Conclusion.tex` (empty), `00Abstract.tex` — own writing.
- `08Discussion.tex` — own writing except item 24.

---

## Summary of remaining work
- **Tier 1:** all 7 resolved. ✅
- **Tier 2:** item 11 resolved; items 8, 9, 10, 12, 13, 14, 15, 16, 17, 18, 19, 20 still open. ⚠️
- **Tier 3:** items 21, 22, 23, 24 — low priority. ◻️
