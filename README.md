# APP 1.4 ontology and Australian health privacy policy corpus

Research materials for **An APP 1.4 Ontology and Labelled Corpus for Assessing Australian Health Privacy Policies: A Blind Test of Rules and Learning**.

This repository preserves the supplied November 2026 research package and adds a working, dependency-free command-line interface for assessing new plain-text policies with ontology v2.1, integrity validation, tests, and GitHub Actions.

## Quick start

Python 3.11 or later. No third-party packages are required for the assessment CLI or repository checks.

```bash
python tools/validate_package.py
python -m unittest discover -s tests -v
python tools/assess_policy.py /path/to/new-policy.txt --output assessment.json
```

The output includes seven disclosure labels, evidence sentence identifiers, traces, detected concepts, and the numbered sentences used for the assessment. Output files must be new to prevent accidental replacement. Labels are research predictions; they do not establish legal compliance.

## Repository map

| Location | Contents |
|---|---|
| `1_Paper/` | Manuscript PDF, LaTeX source and bibliography |
| `2_Notes/` | Claims, novelty review and future work |
| `3_Data/` | 199 policy texts, labels, annotation history and collection scripts |
| `4_Ontology/` | Original ontology v2.1 code, OWL/SKOS/SHACL artifacts and checks |
| `5_Experiments/` | Frozen protocols, historical experiment scripts, saved results and LLM outputs |
| `tools/` | New assessment CLI and package integrity validation |
| `tests/` | Synthetic-input checks; no historical benchmark reruns |

Start with [the handover](README_for_Raza.md), [experiment results](5_Experiments/1_protocols_and_results_summary/RESULTS.md), and [ontology documentation](4_Ontology/README.md).

## Scientific preservation and reproducibility

The 40-policy historical test set is closed. CI does not train, tune, score that set, or call an LLM API. The new CLI refuses inputs located inside its historical test directory. This is a workflow guard, not a prohibition on inspecting the archived materials.

The supplied research files are preserved byte-for-byte, except removal of macOS filesystem metadata. `SOURCE_MANIFEST.json` records their SHA-256 checksums. The CLI reuses the original ontology and the original sentence-splitting function; it does not change cues or scientific results.

**Historical experiment execution is not restored by this repository.** The handover states that the original project folder is required. Its scripts reference missing original paths, collection manifests, helper modules and model caches; some also enforce frozen hashes. They remain research provenance, not working reproduction commands. Do not remove their freeze checks or interpret syntax validation as reproduction of the paper. See [reproducibility notes](REPRODUCIBILITY.md).

## Rights and release status

Keep this repository private initially. No license was included in the supplied package, and this import does not grant a new license over the manuscript, third-party policies, data, or code. Author and affiliation details, venue, release permissions and a permanent ontology namespace remain release decisions. The existing `example.org` ontology namespace is preserved for consistency with archived artifacts.
