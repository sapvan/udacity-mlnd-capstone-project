# Steps to run the project

```
conda env create -f requirements/blog-linux-gpu.yml
source activate blog-bot
KERAS_BACKEND=tensorflow python -c "from keras import backend"
jupyter notebook blog_bot.ipynb
```
