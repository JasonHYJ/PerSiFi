# PerSiFi

Supporting materials for the PerSiFi manuscript on continuous IoT device identification from idle network traffic.

## Current contents

This repository provides manuscript figures and the available source data for Figures 5 and 7. The figure-source files are plotting inputs and derived summaries; they are not packet captures or per-sample classification logs.

| Directory | Contents | Current status |
| --- | --- | --- |
| [figures](figures/) | Manuscript PDF figures and additional SVG/PNG exports for Figures 5 and 7 | Available |
| [data/figure_source](data/figure_source/) | Figure 5 period entries, density curve and metadata; Figure 7 checkpoint counts and proportions | Available |
| [data/datasets](data/datasets/) | Original dataset access information and space for shareable data subsets | Documentation only; no traffic data uploaded |
| [data/splits](data/splits/) | Device, date, record and evaluation-split manifests | Documentation only; manifests not uploaded |
| [results](results/) | Evaluation outputs, per-run summaries and per-sample predictions | Documentation only; result files not uploaded |
| [code](code/) | Code availability information | Documentation only; no source code uploaded |

Directories without data contain a README so that their purpose and status remain visible in Git. Their presence does not indicate that the corresponding materials have been released.

## Source datasets

The study uses the independently published Mon(IoT)r and UNSW IoT traffic datasets. Refer to their original providers for access and reuse terms:

- Mon(IoT)r: <https://moniotrlab.khoury.northeastern.edu/publications/imc19/>
- UNSW IoT traces: <https://iotanalytics.unsw.edu.au/iottraces.html>

Original packet captures are not redistributed in this repository.

## Figure data

See [the source-data documentation](data/figure_source/README.md) for variable definitions, units and the scope of each file. Figure 5 includes 73 exact period values and seven entries recorded only as `>7200`; the latter are excluded from the density estimate. Figure 7 reports checkpoint-level counts for 885 observation records.

The supplied material supports inspection of these figures. It does not provide a complete implementation or an end-to-end reproduction package for all manuscript experiments.

## Code availability

Source code, including the full device-identification implementation and plotting scripts, is not included in this release. Any future code release will be announced here in line with the project's release arrangements; no release date is currently specified.

## File integrity and versioning

[MANIFEST.csv](MANIFEST.csv) lists the published figure and source-data files, their sizes in bytes and SHA-256 checksums. Cite a specific repository commit when referring to these materials, so the exact version can be identified.

## Reuse

The original datasets remain subject to their providers' terms. This repository does not grant additional rights to third-party datasets. No separate reuse license for the deposited material has been specified in this release.
