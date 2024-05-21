# TAPGFD_ML_tutorial

Tutorial material for the ICTS TAGFD program (https://www.icts.res.in/program/TAPGFD). With code/material/memes contributed by Fei Er Yan [@Decenov](https://www.github.com/Decenov) and Han Wang [@hannnwang](https://www.github.com/hannnwang).

Step zero is to get the data. I've been lazy and just uploaded an Argo pack onto a Google Drive, which you can access [here](https://drive.google.com/drive/folders/1JJ0cpshu6-JE8wp93UsHuqy6V33rQy7s?usp=sharing). You'll need to download the whole pack for the above, see picture below.

![Google Drive pointer](https://i.imgur.com/QLpt4MM.png)

There there are at least three known ways of running these:

1) On your computer, `git clone` this repository, then in the load data part, point to where your data folder is (or move the data to where the notebook folder is going to live). Then you can do `git pull` you get updates (if any). You may or may not want to fork the repository (need a GitHub account), then you can in principle contribute material too!

2) On your computer, by downloading the pack (there should be a green "code" button near the top right of this page, click it and there should be "download"). Point to data as above.

3) Via Google colab, but read everything below first! You will need to have a Google account prior to the next steps. If you click the "Colab" button below, it will open a copy of the notebook, to be run through your own Google account. 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/julianmak/TAPGFD_ML_tutorial/blob/main/TAPGFD_ML_tutorial.ipynb) (requires Google login)

Now in your own Google Drive somewhere, upload the data folder from step zero (don't zip, just upload the whole .zarr folder)

When you are in the instance on Google Colab, mount the contents in your Google drive to your instance by adding the following code in the Notebook:

```
from google.colab import drive
drive.mount('/content/drive')

```
When running this step, Google will likely ask you for permissions -- please give it access. If this step is successful, you should see somthing like "Mounted at /content/drive" in the response.

Find the path of the data folder, and take a note of the path of the data (see diagram below; my path happens to be different from '/content/drive/....'.)

![Google Drive folder path](https://i.imgur.com/GIJ7Kna.png)

Then you change the load path accordingly, in this command that can be found in the notebook:

```
data = xr.open_zarr("/path/to/folder/GLOB_HOMOGENEOUS_variables.zarr/")
```
