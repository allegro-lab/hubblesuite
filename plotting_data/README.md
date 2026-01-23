# Plotting Data

```python
models = [
    'allegrolab__hubble-1b-100b_toks-standard-hf',
    'allegrolab__hubble-1b-100b_toks-perturbed-hf',
    'allegrolab__hubble-1b-500b_toks-standard-hf',
    'allegrolab__hubble-1b-500b_toks-perturbed-hf',
    'allegrolab__hubble-8b-100b_toks-standard-hf',
    'allegrolab__hubble-8b-100b_toks-perturbed-hf',
    'allegrolab__hubble-8b-500b_toks-standard-hf',
    'allegrolab__hubble-8b-500b_toks-perturbed-hf',
    # Injectrange
    'allegrolab__hubble-1b-100b_toks-injectrange_0_25-hf',
    'allegrolab__hubble-1b-100b_toks-injectrange_25_50-hf',
    'allegrolab__hubble-1b-100b_toks-injectrange_50_75-hf',
    'allegrolab__hubble-1b-100b_toks-injectrange_75_100-hf',
    'allegrolab__hubble-1b-100b_toks-injectrange_0_50-hf',
    'allegrolab__hubble-1b-100b_toks-injectrange_50_100-hf',
    # Architecture
    'allegrolab__hubble-1b-100b_toks-half_depth-standard-hf',
    'allegrolab__hubble-1b-100b_toks-half_depth-perturbed-hf',
    'allegrolab__hubble-1b-100b_toks-double_depth-standard-hf',
    'allegrolab__hubble-1b-100b_toks-double_depth-perturbed-hf',
    # Paraphrase
    'allegrolab__hubble-1b-100b_toks-paraphrased-perturbed-hf',
    'allegrolab__hubble-8b-100b_toks-paraphrased-perturbed-hf',
    # Interference
    'allegrolab__hubble-1b-100b_toks-interference_testset-hf',
    'allegrolab__hubble-1b-100b_toks-interference_copyright-hf',
    'allegrolab__hubble-1b-100b_toks-interference_privacy-hf',
]
```

## Tasks per File

### File: `copyright_passages.csv`

```python
copyright_tasks = [
    "wikipedia",
    "gutenberg_unpopular",
    "gutenberg_popular",
]

# s100 means evaluated on the 100-suffix tokens after the 50-word prefix
reported_metrics = [
    'norm_ll_byte', 'exact_match_tokens_s100', 'rougeL_f1_s100',
]

all_metrics = [
    'norm_ll_word', 'norm_ll_byte',
    'rougeL_f1', 'rougeL_precision', 'rougeL_recall',
    'rougeL_f1_stemmed', 'rougeL_precision_stemmed', 'rougeL_recall_stemmed',
    'exact_match_tokens',
    'exact_match_tokens_s100', 'rougeL_f1_s100', 'rougeL_recall_s100', 'rougeL_precision_s100'
]
```

### File: `copyright_paraphrases.csv`

```python
copyright_tasks = [
    "wikipedia",
    "gutenberg_unpopular",
    "gutenberg_popular",
    "paws",
    "mrpc",
]

reported_metrics =[
    'norm_ll_byte',  # For copyright tasks
    'acc'            # For paraphrase tasks
]

all_metrics =[
    'norm_ll_word', 'norm_ll_byte', 'acc', 'acc_norm'
]
```

### File: `copyright_checkpoints.csv`

- Additional key for  `checkpoint`

```python
copyright_tasks = [
    "paws",
    "mrpc",
]

reported_metrics =[
    'acc', 'acc_norm'
]
```

### File: `testset.csv`

```python
testset_tasks = [
    "popqa",
    "winogrande_infill",
    "winogrande_infill_on_mcq",
    "winogrande_mcq",
    "winogrande_mcq_on_infill",
    "hellaswag",
    "mmlu",
    "piqa",
    "ellie",
    "ellie_gen",
    "munch",
    "munch_ppl",
]

reported_metrics = [
    'perplexity',
    'acc', 'acc_norm', 'acc_mutual_info',
    'exact_match', 'squad_f1', 'squad_recall', 'prefix_match']
```

### File: `privacy.csv`

```python
privacy_tasks = [
    # YAGO MCQ eval
    "yago_full_prefix_full_suffix",
    "yago_full_prefix_no_suffix",
    "yago_intro_prefix_no_suffix",
    "yago_name_only_prefix_no_suffix",
    # YAGO generative eval
    "yago_full_prefix_gen",
    "yago_intro_prefix_gen",
    "yago_name_only_prefix_gen",
    # YAGO biography loss
    "yago_bio_perplexity",


    # ECTHR document perplexity
    "ecthr_perplexity",
    # ECTHR generative eval
    "ecthr_full_prefix_gen",
    
    # PersonaChat MCQ eval
    "personachat_username_sp",
    "personachat_username_prompted_sp",
    "personachat_mcq",
    "personachat_prompted_mcq",
    # PersonaChat persona perlexity (conditioned on username)
    "personachat_persona_loss",
    # PersonaChat chat perlexity
    "personachat_ppl",
]

reported_metrics = [
    'squad_recall',  # For generative evals
    'norm_ll_byte',  # For perplexity evals
    'acc',           # For MCQ evals
]

all_metrics = [
    'exact_match', 'squad_f1', 'squad_recall', 'prefix_match',
    'norm_ll_word', 'norm_ll_byte', 'acc', 'acc_norm', 'acc_mutual_info', 
    'perplexity'
]
```