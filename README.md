# CERT-Search experimental data and replay code

Companion data for **Exact Terminal Certificates for Adaptive Search with Baseline Task Retention**, by Shuai Liu, Hui Li and Jin Qian.

## Download the frozen data

Use the [versioned release v1-data-20261117](https://github.com/timefly-1989/cert-search-experiments/releases/tag/v1-data-20261117). Download **CERT_Search_Experiments_v1_20261117.zip** (141,933,189 bytes), extract it, and read the included README.md. The automatic GitHub source-code ZIP contains this repository documentation; the experimental data are in the named release asset.

The release includes frozen prepared inputs, separate assay response environments, 1,664 completed registered runs and query traces, generated-law results, support-fold and baseline-quality diagnostics, configurations, and replay/audit scripts. It excludes manuscript files and submission correspondence.

SHA-256: `6f06dc875cc8582f5e908d89693bbc6244ce41c400ab22b0b36d53606fe8b664`

## Verify after extraction

From the extracted CERT_Search_Experiments_v1 directory, use Python with NumPy and pandas:

```sh
python verify_release.py
python experiments/80_followup_validation_20261113/source/audit_outputs.py --complete
python experiments/88_review_revision_20261114/source/analyse_revision.py
```

The archive manifest covers 4,284 payload files. The independent audit checked all 1,664 registered runs and 1,297,272 queries; all 1,338 protected runs had zero baseline task losses. The descriptive analysis checked 882 stored traces / 239,520 selected responses. These checks do not rerun fitting or acquire new biological measurements.

Full replay additionally needs the recorded PyTorch/scikit-learn/SciPy environment; original preprocessing needs RDKit and upstream source data. Prepared-input replay does not reconstruct every historical preprocessing step. Device, numerical library and near-tie differences may change newly executed query sequences and timings. See the retained experiment notes for cold-refit instructions and limitations.

## Sources and rights

The study uses public PKIS2, FS-Mol and MoleculeNet resources. Attribution, transformations, the FS-Mol CC BY-SA 3.0 terms, and file-specific upstream rights are recorded in third_party_notices/ inside the data archive. Third-party GLARE source is not redistributed; its optional upstream URLs and hashes are supplied. No blanket new license is asserted for this mixed-source collection.

These are retrospective computational studies. Seeds and splits are not independent biological replications. No manuscript preprint, new measurement, model-correctness certification or new experimental result is created by this data release.
