# SentenceSmith Processing Pipeline

This repository contains the **SentenceSmith** data generation pipeline, which automatically creates **semantically controlled sentence pairs** for evaluating text embedding models.  

The main script, **`process.sh`**, runs the full workflow: parsing sentences, converting them to AMR graphs, applying structured edits, regenerating modified sentences, and saving the results.

---

## Overview

Given an input text file with sentences, the pipeline automatically produces modified versions under several linguistic transformations (e.g., hypernym, antonym, or polarity changes).  

Each output record includes:
- The **original sentence**
- The **modified sentence**
- The **type of modification**
- The **semantic relationship** between them  

All results are saved in a CSV file for easy evaluation.

---

## Pipeline Summary

1. **Input setup** — The script takes three command-line arguments:  
   ```bash
   ./process.sh <input_file> <output_file> <intermediate_dir>
The input file should contain one sentence per line.
The script creates the specified output CSV file (with headers) and an intermediate directory to store all temporary AMR and triple representations.
2. **AMR conversion** — Converts sentences into Abstract Meaning Representation (AMR) graphs.  
3. **Triples extraction** — Transforms AMRs into subject–relation–object triples.  
4. **Linguistic edits** — Applies controlled modifications (e.g., hypernym, antonym, negation).  
5. **Sentence regeneration** — Converts modified triples back into sentences.  
6. **Semantic relation check** — Assesses how the modified sentence relates to the original.  
7. **Output** — Logs all results into a CSV file and saves intermediate files for inspection.

---

## Usage

Run the pipeline with:

```bash
./process.sh <input_file> <output_file> <intermediate_dir>
```
Example:
```
./process.sh chatgpt_inputs.txt output_sentences_all.csv intermediate_results_all
```
After processing, the script will display:
```
Processing complete.
Results saved to output_sentences_all.csv
Intermediate results saved to intermediate_results_all/
```

## 📝 Output Format

Each line in the output CSV follows the structure:


**Example:**

| Original Sentence | Modified Sentence | Modification Type | Semantic Relationship |
|-------------------|------------------|-------------------|-----------------------|
| The dog is happy. | The dog is sad.  | antonym           | contrast              |
| She walks fast.   | She does not walk fast. | polarity_negation | negation |

## Extension Notes:

You can adjust the modification types in the script:
```
modifications=("RD" "hypernym" "polarity_negation" "RS" "antonym")
```

to extend, you should also change the subsequent code to support your newly added modifications.

