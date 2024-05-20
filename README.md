# TAPGFD_ML_tutorial

Tutorial material for the ICTS TAGFD program (https://www.icts.res.in/program/TAPGFD). With code/material/memes contributed by Fei Er Yan [@Decenov](https://www.github.com/Decenov) and Han Wang [@hannnwang](https://www.github.com/hannnwang).

Step zero is to get the data. I've been lazy and just uploaded an Argo pack onto a Google Drive, which you can access [here](https://drive.google.com/drive/folders/1JJ0cpshu6-JE8wp93UsHuqy6V33rQy7s?usp=sharing). You'll need to download the whole pack for the above, see picture below.

![Google Drive pointer](https://i.imgur.com/QLpt4MM.png)

There there are at least three known ways of running these:

1) On your computer, `git clone` this repository, then in the load data part, point to where your data folder is (or move the data to where the notebook folder is going to live). Then you can do `git pull` you get updates (if any). You may or may not want to fork the repository (need a GitHub account), then you can in principle contribute material too!

2) On your computer, by downloading the pack (there should be a green "code" button near the top right of this page, click it and there should be "download"). Point to data as above.

3) Via Google colab, but read everything below first! You will need to pull and upload copies code and data accordingly. If you click the "Colab" button below it will open a temporary instance (that is not saved):

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/julianmak/TAPGFD_ML_tutorial/blob/main/) (requires Google login)

I would highly recommend you don't use the temporary instance, and instead do this through your own Google drive (reasons to be elaborated on). For that, you need a Google account. Supposing you have it, then first, in the temporary instance:

a) upper left of screen, "File -> Save a copy in Drive" (which will then open another window probably, but now the copy should be in your account)

b) now in your own Google Drive somewhere, upload the data folder from step 0 (don't zip, upload the whole folder)

c) do a mount of your Google drive by adding the following code in the Notebook:

```
from google.colab import drive
drive.mount('/content/drive')

```
When running this step, Google will likely ask you for permissions -- please give it access. If this step is successful, you should see somthing like "Mounted at /content/drive" in the response.


Find the path of the data folder, and take a note of the path (see diagram below; mine happens to be somewhere else)

![Google Drive folder path](https://i.imgur.com/GIJ7Kna.png)

Then you change the load path accordingly, in this command that is in the notebook:

```
data = xr.open_zarr("/path/to/folder/GLOB_HOMOGENEOUS_variables.zarr/")
```

There are also some other things that you need to pay attention to if running on Colab. See the included notebook for related codes.
