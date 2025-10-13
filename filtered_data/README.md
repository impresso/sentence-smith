# Filtered Data

This directory contains **quality-controlled evaluation data** validated by the faithfulness detector.

---

## Files

| File | Source | Rows | Description |
|------|--------|------|-------------|
| `chatgpt_test_samples_11456x6.csv` | ChatGPT | 11,456 | Quality-controlled ChatGPT data for evaluation |
| `paws_samples_1737x6.csv` | PAWS | 1,737 | Quality-controlled PAWS data for evaluation |

---

## Format

All files have 6 columns:
```
original_sentence,modified_sentence,modification_type,semantic_relationship,paraphrase,source_file
```

- `original_sentence`: Original sentence before modification
- `modified_sentence`: Sentence after controlled modification
- `modification_type`: Type of edit (RD, RS, hypernym, antonym, polarity_negation)
- `semantic_relationship`: NLI model prediction with confidence
- `paraphrase`: Paraphrase of the original sentence
- `source_file`: Source file from `../raw_data/`

---

## Usage

See `../test_process.ipynb` for examples of using this data to evaluate embedding models.
