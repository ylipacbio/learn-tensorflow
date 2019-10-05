Script below installs python 3.7.4 and Tensorflow and relavant useful packages on macbook.

1) Install python 3.7.4
2) Create virtual env and activate this virtual env for tensorflow
3) Install tensorflow 2.0.0 in virtual env
4) Install general python packages for syntax checking, formating
5) Install python packages for data manipulation
6) Install tools to visualize tensor flow models
7) Install useful IDE: Jupyter notebook and launch it

```
function install_tf_on_mac() {
echo "Brew install python3"
python3 --version
# python 3.7.4

echo "Create virtual env for tensorflow"
python3 -m venv ~/venv/tf

echo "Activate tensor flow virtual env"
source ~/venv/tf/bin/activate
which python3
# ~/venv/tf/bin/python

echo "upgrade pip"
pip install --upgrade pip

echo "install tensorflow"
pip install tensorflow==2.0
python -c 'import tensorflow as tf; print(tf.__version__)'
# 2.0.0

echo "install useful py packages"
pip install pylint autopep8 pytest ipython jupyterlab 
echo "install tools for data manipulation"
pip install seaborn pandas

echo "install tools for keras model visualization"
pip install pydot=1.2.3 matplotlib
# Note pydot 1.2.4 has a bug which is not compatible with tf 2.0
brew install graphvis

echo "Launch jupyter notebook"
juypter notebook&
}
```
