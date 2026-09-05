# dg-evidence-750

**750 expert-audited claim–passage pairs**: 150 financial claims × 5 web passages published on or before each claim date.

The dataset distinguishes topical relevance from **decision-grade evidence**: credible, temporally valid, claim-matched evidence that is independently sufficient to support or refute a claim.

## Data: `dg-evidence-750.jsonl`

## Labels

| Label | Meaning | Pairs |
|---|---|---:|
| 0 | Irrelevant | 302 |
| 1 | Relevant but insufficient | 298 |
| 2 | Decision-grade support | 71 |
| 3 | Decision-grade refute | 79 |

## Fields

| Field | Description |
|---|---|
| `item_id`, `claim_id` | Pair and claim identifiers. |
| `claim`, `claim_date` | Claim text and posting date (evidence cutoff). |
| `source_title`, `domain`, `source_date` | Passage provenance; `source_date ≤ claim_date`. |
| `passage` | Evidence passage. |
| `final_label`, `final_label_name` | Numeric label and its name. |
| `relevance_target` | `1` for labels 1–3; otherwise `0`. |
| `decision_grade_target` | `1` for labels 2–3; otherwise `0`. |
| `direction` | `"support"` for label 2, `"refute"` for label 3; otherwise `null`. |

## Provenance

Claims come from the **Fin-Fact training split**. Passages were retrieved through claim-only web search from publicly accessible pages and frozen after a label-blind integrity audit. Two blinded annotators labelled all pairs, followed by full expert audit and adjudication.