# ldsands-spark-recipes

## Benchmarking

```sh
# to run it locally solo (Note that -H localhost will also imply --solo)
sparkrun benchmark <recipe_filename> -H localhost
# add a different cache dir
sparkrun benchmark <recipe_filename> -H localhost --cache-dir $env.EXTERNAL_HUGGINGFACE_MODELS_DIR
# use the spark arena benchmark profile
sparkrun benchmark <recipe_filename> -H localhost --profile spark-arena-v1
# use Ray dashboard (default port: 8265)
sparkrun benchmark <recipe_filename> -H localhost --dashboard
# combination commands to use
sparkrun benchmark <recipe_filename> -H localhost --profile spark-arena-v1 --dashboard
sparkrun benchmark <recipe_filename> -H localhost --cache-dir $env.EXTERNAL_HUGGINGFACE_MODELS_DIR --profile spark-arena-v1 --dashboard
```

## Setup

```sh
sparkrun cluster create myspark_local_cache --hosts localhost
# if the below doesn't work then you may have to use sudo
sparkrun setup fix-permissions --cluster myspark_local_cache
# if you see "Could not clear page cache" then use the command below
sparkrun setup clear-cache --save-sudo --hosts myspark_local_cache
# if that doesn't work then try the below
chmod -R 755 ~/.cache/huggingface/

sparkrun cluster create myspark_external_cache --hosts localhost --cache-dir $env.EXTERNAL_HUGGINGFACE_MODELS_DIR
# if the below doesn't work then you may have to use sudo
sparkrun setup fix-permissions --cluster myspark_external_cache
# if you see "Could not clear page cache" then use the command below
sparkrun setup clear-cache --save-sudo --hosts myspark_external_cache
# if that doesn't work then try the below
chmod -R 755 $env.EXTERNAL_HUGGINGFACE_MODELS_DIR


```
