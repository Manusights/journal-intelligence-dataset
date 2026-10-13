# Journal intelligence dataset: 57 journals, with confidence marked on every figure

> **Newer, sourced tables (October 2026).** This repo is an early snapshot (data version 2026.03.30) whose figures are mostly estimates, as the table below says. The maintained tables now link every figure to the journal's or a study's own published source: [desk-rejection rates for 88 journals](https://manusights.com/blog/desk-rejection-rate-by-journal) and [AI-use policies for 100 journals](https://manusights.com/blog/journal-ai-policies-2026). Use those for anything you plan to cite. This snapshot stays here unchanged so earlier citations still resolve.

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Data version](https://img.shields.io/badge/data-2026.03.30--mvp1-blue.svg)](./data)

Acceptance rates, review timelines, desk-rejection rates, and submission limits for **57 journals across 23 publishers and 17 fields**.

## Read this before you use the numbers

Most tables of journal acceptance rates present every figure as though it were equally solid. They are not. This dataset marks the evidence type on each one, and the honest headline is what that typing reveals:

| Field | official | reported | estimated |
|---|---:|---:|---:|
| Acceptance rate | 0 | 4 | **53** |
| Review time | 1 | 4 | **52** |
| Desk-rejection rate | 0 | 0 | **57** |

**Not one of the 57 desk-rejection rates is officially published.** Every one is an estimate. Four journals report an acceptance rate; one publishes an official review time.

So the value here is not that our acceptance rates are better than anyone else's. It is that you can see which figures are load-bearing and which are inference, and cite accordingly. If you need an authoritative acceptance rate for a specific journal, go to the publisher. This dataset tells you whether the publisher actually says.

If you want one number from this repo, take that one: **the data researchers are told to use when choosing a journal is largely not published by the journals.**

## Evidence typing

Three columns carry a `_Type` sibling: `Acceptance Rate Type`, `Review Time Type`, `Desk Reject Rate Type`.

| Value | Meaning |
|---|---|
| `official` | Stated by the publisher or journal on a page we can cite. |
| `reported` | Appears in a credible secondary source (editorial, annual report, published survey) but not on an official journal page. |
| `estimated` | Our inference from field norms, publisher patterns, and comparable journals. **Not a measurement.** |
| `unknown` | Schema value; not present in this release. |

Two further columns describe the record as a whole: `Source Confidence` (`mixed` for 55 records, `medium` for 2) and `Source Count`.

## Contents

| File | Rows | Notes |
|---|---:|---|
| [`data/journal-intelligence-2026.03.30-mvp1.csv`](./data/journal-intelligence-2026.03.30-mvp1.csv) | 57 | 26 columns. Human-readable display strings. |
| [`data/journal-intelligence-2026.03.30-mvp1.json`](./data/journal-intelligence-2026.03.30-mvp1.json) | 57 | 29 fields. Adds numeric day counts (`reviewTimeDeskDays`, `reviewTimeFirstDecisionDays`) and array fields (`fitSignals`, `commonRejectionReasons`) that the CSV flattens. **Use the JSON for analysis.** |

Both are generated from the same source of record and carry version tag `2026.03.30-mvp1`.

### Columns

`Journal Slug` · `Journal Name` · `Publisher` · `Primary Field` · `Open Access Model` · `Impact Factor` · `Acceptance Rate` (+`Type`) · `Desk Decision` · `First Decision After Review` (+`Review Time Type`) · `Desk Reject Rate` (+`Type`) · `Submission Word Limit` · `Abstract Format` · `Abstract Word Limit` · `Figure Limit` · `Reference Limit` · `Difficulty Score` · `Difficulty Band` · `Primary Fit Signal` · `Primary Rejection Reason` · `Source Confidence` · `Source Count` · `Last Reviewed` · `Version`

`Difficulty Score`, `Difficulty Band`, `Primary Fit Signal` and `Primary Rejection Reason` are **Manusights editorial judgments**, not third-party data. They come from our pre-submission review work. Treat them as opinion with a stated basis, not as measurement.

## What this is good for, and what it is not

**Reasonable uses:** shortlisting candidate journals by field and difficulty band; comparing submission limits across publishers; teaching submission strategy; a starting point for a systematic acceptance-rate study that then verifies against publishers.

**Not appropriate:** citing a specific `estimated` acceptance rate as a fact about that journal; bibliometric analysis that treats the estimated columns as measured; any claim of comprehensiveness. 57 journals is a starting panel, not a census.

## Coverage

23 publishers, 17 primary fields, 57 journals. Selection favoured journals researchers most often ask us about, which skews toward high-profile venues. It is not a random or representative sample of the literature.

## How to cite

> Manusights. (2026). *Journal intelligence dataset: acceptance rates, review times and desk-rejection rates for 57 journals, with per-figure evidence typing* (Version 2026.03.30-mvp1) [Data set]. https://manusights.com/resources/journal-intelligence

```bibtex
@misc{manusights2026journalintelligence,
  title   = {Journal Intelligence Dataset: Acceptance Rates, Review Times and
             Desk-Rejection Rates for 57 Journals, with Per-Figure Evidence Typing},
  author  = {{Manusights}},
  year    = {2026},
  version = {2026.03.30-mvp1},
  note    = {Data set. Evidence type marked per figure; most acceptance and all
             desk-rejection rates are estimates, not publisher-stated values.},
  url     = {https://manusights.com/resources/journal-intelligence}
}
```

Please carry the evidence-typing caveat into any work that reuses these figures. It is the reason the dataset is worth citing and the reason it can be misused.

## Corrections

If you have an official figure that contradicts an `estimated` one here, open an issue or email erik@manusights.com. A publisher-stated number will replace an estimate in the next version, with the type upgraded to `official`.

## License

[CC BY 4.0](./LICENSE). Reuse freely with attribution.

## Related

- Live tables: https://manusights.com/acceptance-rates and https://manusights.com/review-timelines
- Retracted-citation study (12,402 papers, 54 journals): https://github.com/Manusights/retracted-citation-study
- Citation metadata for the Manusights service: https://github.com/Manusights/manusights-citation
