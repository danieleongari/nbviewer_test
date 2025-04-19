# nbviewer testing

## Instruction
1. Commit an push the notebook
2. Go to `https://nbviewer.jupyter.org/github/{user}/{repo}/blob/{commit}/{path/to/notebook}` for a specific commit
3. Go to `https://nbviewer.jupyter.org/github/{user}/{repo}/tree/{branch}/` for the latest commit (also `/blob/{branch}/` instead of `/tree/{branch}/` is fine)

## Issues and unexpected behavior

It is not clear how often the cache is updated: many issues [report this problem](https://github.com/jupyter/nbviewer/issues). <br>
The [FAQ tells](https://nbviewer.org/faq#why-is-nbviewer-showing-an-outdated-version-of-my-notebook) that I should append `?flush_cache=true` to the URL but this was not effective to me.  <br>
The best way I found is to first go the commit verson (see Intructions, Step 2) and this creates the notebook visualization faster.

Another issue is with VSCode and Plotly: [to render the plots correctly](https://nbviewer.org/github/danieleongari/nbviewer_test/blob/40b322184fb614dc67cbf912096a41ba16c59a92/12_plotly_slider2_all.ipynb) you need to use
```python
import plotly.io as pio
pio.renderers.default = 'notebook+vscode'
```

## nbviewer links
- [All notebooks](https://nbviewer.org/github/danieleongari/nbviewer_test/tree/main/)
- [All notebooks (commit `867571a2`)](https://nbviewer.org/github/danieleongari/nbviewer_test/tree/867571a2140143aed461a1b8533f088eeec0233e/)
- [Notebook, last commit](https://nbviewer.org/github/danieleongari/nbviewer_test/tree/main/notebook_1.ipynb)
- [Notebook, commit `867571a2`](https://nbviewer.org/github/danieleongari/nbviewer_test/blob/867571a2140143aed461a1b8533f088eeec0233e/notebook_1.ipynb)