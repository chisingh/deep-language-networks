# Variational Inference

## Setup

Please follow the instructions from the [main README](../../README.md).


## Reproducing results


### One-Layer DLN

See [one-layer-dln-hp-search-result.json](./one-layer-dln-hp-search-result.json) for available datasets and the hyperparameter search results. Then run:

    python scripts/one_layer/one_layer.py --dataset <dataset_id>


### Two-Layer DLN

For two-layer DLN, you can select one of the following training strategies:

- `two_layers_fix_2nd`: Load pretrained prompts from [one-layer-dln-hp-search-result.json](./one-layer-dln-hp-search-result.json) to the second layer and train only the first layer.

- `two_layers_ft_2nd`: Load pretrained prompts from [one-layer-dln-hp-search-result.json](./one-layer-dln-hp-search-result.json) to the second layer and train both the first and second layers.

- `two_layers_e2e`: Train the two layers from scratch.

Then, run the following command:

    bash scripts/<training_strategy>/<dataset_id>.sh

Results will be saved in `log/<training_strategy>/<dataset_id>`.


## Running your own experiments

If you decide to run your own experiments, please check:

    python vi_main.py --help
