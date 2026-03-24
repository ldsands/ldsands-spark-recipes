# ldsands-spark-recipes

## Useful Instructions

```sh
sparkrun benchmark <recipe_filename> --solo
# add a different cache dir
sparkrun benchmark <recipe_filename> --solo --cache-dir $env.EXTERNAL_HUGGINGFACE_MODELS_DIR
# use the spark arena benchmark profile
sparkrun benchmark <recipe_filename> --solo --profile spark-arena-v1
# combination commands to use
sparkrun benchmark <recipe_filename> --solo --cache-dir $env.EXTERNAL_HUGGINGFACE_MODELS_DIR --profile spark-arena-v1
```
