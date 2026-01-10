# Lab Setup

## Client-Server Architecture

Since CPUs are not enough for Deep Learning models; we'll need a GPU. Understanding the client-server interaction is crucial for working with remote code execution environments such as Google Colab.

![](./assets/jupyter-server.png){fig-align="center"}

The image above shows how we interact with remote servers, such as Google Colab, to run our code:

1. We write code in the browser using Jupyter Notebooks or VS Code
2. On save: the code is sent to the Juypter/Colab Server and stored there as `.ipynb` files
3. On run: the code is: 
   1. sent to the kernel for execution
   2. then back to the server to save the results
   3. which are then sent back to the browser

## 0. Google Account

Make sure you have a Google account. And can access [Google Colab](https://colab.research.google.com/notebooks/basic_features_overview.ipynb#scrollTo=KR921S_OQSHG). 

## 1. Upload Lab Files to Google Drive

Then, you will upload lab files to your Google Drive: `Bootcamp/W4_DL/`, and the folder tree will look like this:

```
Bootcamp/
├── W4_DL/                                 # Your Bootcamp folder
   ├── assets/                             # Contains images and other assets
   ├── C1_M1_Getting_Started               # Course 1 Module 1: Getting Started
   │   ├── C1_M1_Lab_1_simple_nn           # Lab 1: Building a Simple Neural Network
   │   │   ├── C1_M1_Lab_1_simple_nn.ipynb # The notebook file
   │   │   └── helper_utils.py             # A Python module for helper functions
```

## 2. Mount Google Drive

Inside your **Colab Notebook**, run the following code cell. It will prompt you to grant permission for Colab to access your Drive files.

```python
from google.colab import drive
drive.mount('/content/drive')
```

Any files you save or modify in this directory will be saved directly to your Google Drive.

## 3. Change Working Directory

Once mounted, your files are accessible under `/content/drive/MyDrive/`. Use the `%cd` magic command to move into your specific lab folder. Note that if your folder names contain spaces, you should wrap the path in quotes.

```sh
%cd "/content/drive/MyDrive/Bootcamp/W4_DL/C1_M1_Getting_Started/C1_M1_Lab_1_simple_nn"
```

## 4. Verify Your Files

To confirm you are in the correct location and see your uploaded lab files, run:

```sh
!ls
```

You should see:

- `C1_M1_Lab_1_simple_nn.ipynb`
- `helper_utils.py`

Now that you have changed the directory with `%cd`, you can load datasets or scripts using relative paths (e.g., `pd.read_csv('data/train.csv')`) instead of long absolute paths.

## Optional: Working from inside VS Code instead of the Colab Notebook

[Google Colab for VS Code](https://marketplace.visualstudio.com/items?itemName=google.colab) extension allows you to work in VS Code while the code is sent and executed in Colab servers. However, the steps above are still required.
