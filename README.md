# nbviewer testing

## Instruction
1. Commit an push the notebook
2. Go to `https://nbviewer.jupyter.org/github/{user}/{repo}/blob/{commit}/{path/to/notebook}` for a specific commit
3. Go to `https://nbviewer.jupyter.org/github/{user}/{repo}/tree/{branch}/` for the latest commit (also `/blob/{branch}/` instead of `/tree/{branch}/` is fine)

## Issues and unexpected behavior

It is not clear how often the cache is updated: many issues [report this problem](https://github.com/jupyter/nbviewer/issues). <br>
The [FAQ tells](https://nbviewer.org/faq#why-is-nbviewer-showing-an-outdated-version-of-my-notebook) that I should append `?flush_cache=true` to the URL but this was not effective to me.  <br>
The best way I found is to first go the commit verson (see Intructions, Step 2) and this creates the notebook visualization faster.

Another issue is with VSCode and Plotly: to render the plots correctly you need to use (plotly<6.0):
```python
import plotly.io as pio
pio.renderers.default = 'notebook'
```

However, in plotly>=6.0 the `notebook` and `vscode` renders are different and you need to use `"vscode+notebook"`
- there was a problem mentioned in https://github.com/plotly/plotly.py/issues/4953 and solved by https://github.com/plotly/plotly.py/pull/5096

## nbviewer links
- [All notebooks](https://nbviewer.org/github/danieleongari/nbviewer_test/tree/main/)
- [All notebooks (commit `867571a2`)](https://nbviewer.org/github/danieleongari/nbviewer_test/tree/27e43306b6e35cd3f8dc9bb034c1b9d2b5abf3ce/)
- [Notebook, last commit](https://nbviewer.org/github/danieleongari/nbviewer_test/tree/main/notebook_1.ipynb)
- [Notebook, commit `867571a2`](https://nbviewer.org/github/danieleongari/nbviewer_test/blob/27e43306b6e35cd3f8dc9bb034c1b9d2b5abf3ce/notebook_1.ipynb)