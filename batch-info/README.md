Perturbation Information
---

The files in this directory report the positions of the different inserted perturbations and which dataset the perturbation was sourced from. The important columns are:

- `perturbation_file`: The high-level subset of the pertubation. Corresponds to the tokenized files shared [here](https://huggingface.co/datasets/allegrolab/dclm-baseline-500b_toks/tree/main/tokenized) and [here](https://huggingface.co/datasets/allegrolab/dclm-baseline-500b_toks/tree/main/tokenized_paraphrase)
- `source_task`: The lower level dataset that the inserted perturbation belongs to
- `source_row`: The row within the dataset (according to the corresponding `*_nodup.jsonl` file)
- `insertion_batch`: The batch in pre-training where the example was inserted
- `insertion_sequence`: The exact training sequence where the perturbation was inserted (`insertion_batch` = `insertion_sequence`//1024)
- `pt_window_offset`: Index within all the documents in that training sequence. For example, if the training sequence consisted of 3 documents and the perturbation was inserted between documents 0 and 1, then the offset would be 1
- `pt_injection_len`: The token length of the inserted perturbation
- `orig_doc_seq_sizes`: The token lengths of the documents that made up the original sequence
