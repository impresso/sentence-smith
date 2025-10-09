# SentenceSmith

Codebase for SentenceSmith

## Repository Structure

The repository is organized as follows:

```
├── filtered_data
│   └── The final minimal-pair evaluation data that has been quality controlled by the faithfulness detector.
├── pipeline
│   └── Scripts to generate the data. PARSE -> EDIT -> GENERATE.
├── raw_data
│   └── unprocessed data.
├── util_scripts
│   └── Utility Scripts
```

The file `test_process.ipynb` shows examples for how to evaluate embedding models in the interpretable linguistic categories.

## Citation 

If you like the project, consider citing:

@article{li2025sentence,
  title={Sentence Smith: Controllable Edits for Evaluating Text Embedding Models},
  author={Li, Hongji and Michail, Andrianos and Gubelmann, Reto and Clematide, Simon and Opitz, Juri},
  journal={EMNLP (to appear)},
  year={2025}
}

