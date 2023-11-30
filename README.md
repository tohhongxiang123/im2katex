# Image to KaTeX

# Setup

Download data [here](https://zenodo.org/records/56198), place into `data` directory

Then,

```
python -m venv venv
venv/Scripts/activate
pip install pandas numpy matplotlib opencv-python seaborn pylatexenc
```

# Notes

`supported_environments` and `supported_macros` are scraped off [KaTeX's support table](https://katex.org/docs/support_table.html)

# Resources

- https://github.com/phfaist/pylatexenc
- https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Image-Captioning