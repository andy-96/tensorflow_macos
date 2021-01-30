# Installing Tensorflow for M1

## Preparation

1. Use Apple's Python 3.8.2 version. Verify this by checking `which python3`, it should be `/usr/bin/python3`
2. Deactivate anaconda environment, if it is activated
3. Download `.tar.gz` archive: https://github.com/apple/tensorflow_macos/releases (Current version: `v0.1alpha1`)
4. Change all files under `tensorflow_macos/arm64` from `*-cp38-macosx_11_0_*.whl` to `*-cp38-macosx_10_16_*.whl`
5. Replace this repo's install script `./install_venv.sh` with original one

## Using Python's venv

1. Cd into your project repo
2. Create virtual environment: `python3 -m venv .venv`
3. Make sure the used python version in your venv is `python 3.8` if you have other Python versions installed
4. Run `<path-to-tensorflow_macos>/tensorflow_macos/install_venv.sh` and use `<path-to-project>/.venv` as the venv folder
5. Activate venv: `.venv/bin/activate`

## Using Pipenv

1. Cd into your project repo
2. Create virtual environment: `pipenv --python 3.8`
3. Run `pipenv shell` and copy the virtualenv path
4. Run ``<path-to-tensorflow_macos>/tensorflow_macos/install_venv.sh` and use the virtualenv path

## Test whether it worked

1. Activate virtualenv
2. Run `python`
3. `import tensorflow as tf`
4. `print(tf.constant(4))`
