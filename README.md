# dg-evidence-750

`dg-evidence-750.jsonl` (JSON Lines) — 750 expert-audited claim–passage pairs
(150 financial claims × 5 pre-cutoff web passages), labelled to separate
topical relevance from **decision-grade** evidence: credible, temporally
valid, claim-matched, and independently sufficient to support or refute the
claim. 137 claims (91.3%) contain a relevant passage; 77 (51.3%) contain a
decision-grade one.

> Anonymized for double-blind review (FinNLP 2026 submission, *Relevant Is
> Not Enough*). Citation added upon publication.

## Schema

| Field | Description |
|---|---|
| `item_id`, `claim_id` | Pair ID; claim ID (`FF150_001`–`FF150_150`). |
| `claim`, `claim_date` | Claim text and posting date (= evidence cutoff). |
| `source_title`, `domain`, `source_date` | Passage provenance; `source_date ≤ claim_date` for all pairs. |
| `passage` | Evidence passage, 55–228 words. |
| `final_label`, `final_label_name` | `0` irrelevant (302) · `1` relevant but insufficient (298) · `2` decision-grade support (71) · `3` decision-grade refute (79). |
| `relevance_target`, `decision_grade_target` | Binary targets `R(y) = 1[y ∈ {1,2,3}]`, `D(y) = 1[y ∈ {2,3}]`. |
| `direction` | `"support"` / `"refute"` for labels 2/3, else `null`. |

## Provenance

Claims come from the Fin-Fact training split; passages were retrieved by
claim-only web search from publicly accessible pre-cutoff pages and frozen
after a label-blind integrity audit. Two blinded annotators (a trained MSc
annotator and a financial risk analyst) labelled all pairs, with full expert
audit and adjudication; full protocol in the paper appendix. Passage excerpts
remain the property of their original publishers and are shared solely to
support review and reproducibility; annotation licensing will be finalised
upon publication.
