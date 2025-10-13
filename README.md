# [Sentence Smith: Controllable Edits for Evaluating Text Embeddings](https://arxiv.org/abs/2502.14734) - Datasets and starter code
<img height="24" alt="emnlp2025 suzhou" src="https://github.com/user-attachments/assets/d3a426b1-a6f7-4ee7-9d42-47595b6f3f65" /> ![License: AGPLV3+](https://img.shields.io/badge/License-AGPLV3+-brightgreen.svg)

---

## Overview

SentenceSmith introduces a framework for generating linguistically controlled minimal pairs of sentences to assess the robustness and interpretability of text embedding models.

This repository accompanies our [EMNLP2025 paper](https://arxiv.org/abs/2502.14734). It provides the datasets and the SentenceSmith foil generation pipeline used to construct a challenging and interpretable evaluation benchmark for embedding models.

---

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Repository Structure](#repository-structure)
- [Citation](#citation)
- [About Impresso](#about-impresso)
- [License](#license)

---

## Installation

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Additionally, download the Spacy English model:

```bash
python -m spacy download en_core_web_sm
```

For AMR models, follow the [amrlib documentation](https://amrlib.readthedocs.io/) to download required models.

---

## Repository Structure

The repository is organized as follows:

```
├── filtered_data
│   └── The final minimal-pair evaluation data that has been quality controlled by the faithfulness detector.
├── sentence_smith_pipeline
│   └── Scripts to generate the data. PARSE -> EDIT -> GENERATE.
├── raw_data
│   └── evaluation data before quality control by the faithfulness detector.
├── util_scripts
│   └── data processing utility scripts.
```

The Jupyter notebook "test_process.ipynb" demonstrates how to evaluate embedding models across interpretable linguistic categories using the provided data.

## Citation

If you use these resources, please cite our paper:

```
@article{li2025sentence,
  title={Sentence Smith: Controllable Edits for Evaluating Text Embedding Models},
  author={Li, Hongji and Michail, Andrianos and Gubelmann, Reto and Clematide, Simon and Opitz, Juri},
  journal={EMNLP (to appear)},
  year={2025}
}
```


## About Impresso

### Impresso project

[Impresso - Media Monitoring of the Past](https://impresso-project.ch) is an interdisciplinary research project that aims to develop and consolidate tools for processing and exploring large collections of media archives across modalities, time, languages and national borders. The first project (2017-2021) was funded by the Swiss National Science Foundation under grant No. [CRSII5_173719](http://p3.snf.ch/project-173719) and the second project (2023-2027) by the SNSF under grant No. [CRSII5_213585](https://data.snf.ch/grants/grant/213585) and the Luxembourg National Research Fund under grant No. 17498891.

### Copyright

Copyright (C) 2025 The Impresso team.

### License

This program is provided as open source under the [GNU Affero General Public License](https://github.com/impresso/impresso-pyindexation/blob/master/LICENSE) v3 or later.

---


