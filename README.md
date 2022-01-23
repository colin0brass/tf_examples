# tf_experiments
Experiments with tensorflow and tflite training and inference

## Installation on Mac
```shell
# ========================
# == TFLite-Model-Maker ==
# ========================
# https://www.tensorflow.org/lite/api_docs/python/tflite_model_maker/object_detector
# On MacBook Pro
pip install virtualenv

virtualenv ~/Envs/tflite_model_maker_env -p python3
# later, to remove:
# rm -Rf ~/Envs/tflite_model_maker_env
source ~/Envs/tflite_model_maker_env/bin/activate
# later, to deactivate:
# deactivate

#pip install -q --use-deprecated=legacy-resolver tflite-model-maker tensorflow-metadata absl-py
#ERROR: pip's legacy dependency resolver does not consider dependency conflicts when selecting packages. This behaviour is the source of the following dependency conflicts.
#tensorflow-metadata 1.5.0 requires absl-py<0.13,>=0.9, but you'll have absl-py 1.0.0 which is incompatible.
pip install --use-deprecated=legacy-resolver tflite-model-maker tensorflow-metadata absl-py==0.12.0

pip check

pip install -q pycocotools

# Make kernel available in Jupyter (as used in classification training)
pip install ipykernel # IPython kernel for Jupyter
python -m ipykernel install --user --name tflite_model_maker_env
# to remove it later:
# jupyter kernelspec list
# jupyter kernelspec remove tflite_model_maker_env

pip install py # to help with finding corrupt images

# Kivy for bird recognition app
pip install kivy

# Modules for bird recognition app
brew install libjpeg
pip install jupyterlab seaborn
pip install astral==1.10.1 # to avoid compatibility problem with v2

pip3 install --extra-index-url https://google-coral.github.io/py-repo/ tflite_runtime
# runtime clash with tensorflow:
# ImportError: generic_type: type "InterpreterWrapper" is already registered!
# suspect can only use in separate environment```
