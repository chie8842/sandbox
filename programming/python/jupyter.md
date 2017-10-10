# Jupyter notebook

## vimのキーバインドを使う方法

```
cd $(jupyter --data-dir)/nbextensions
git clone https://github.com/lambdalisue/jupyter-vim-binding vim_binding
jupyter nbextension enable vim_binding/vim_binding
pyenv local anaconda3-4.2.0
jupyter nbextension enable vim_binding/vim_binding

```
