# MegatronLM Dataset Prepare

## Prepare the dataset

- Checkout `examples/sample_dataset.jsonl` for the format of the dataset.

```js
// examples/sample_dataset.jsonl
{"text": "This is the first sentence."}
{"text": "This is the second sentence."}
// ...
```

## Prepare the Environment

- Install the dependencies

```bash
pip install -r requirements.txt
```

for more details, please checkout [requirements.frozen.txt](requirements.frozen.txt).

## Encode the dataset

- Encode the dataset with the following command
- Check [run.sh](run.sh) for more details

```bash
# Create output directory
mkdir -p data/
# Encode the dataset
python preprocess_data.py \
--input examples/sample_dataset.jsonl \
--tokenizer-type AutoTokenizer \
--vocab-file beomi/llama-2-ko-7b \
--output-prefix data/ \
--dataset-impl mmap \
--workers 100 \
```

## Acknowledgement

This repo codes are partially copied/edited from [EleutherAI/gpt-neox @ 10bf78](https://github.com/EleutherAI/gpt-neox/commit/10bf78871e214f8d0e3bc8662f968e367587a516).
