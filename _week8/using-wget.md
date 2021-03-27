## Optional: Using `wget` to download files from the web

We'll be going over how to download files from GitHub using git, but since a few you you had questions about how to download course files from GitHub, now, I thought I would give you one other tool for downloading material from our course repository (and from other web resources).

**`wget`** is program for downloading files from the web. It's a command that you can run on your command line (on Terminal in Macs or in Powershell on Windows) and you can use it to download individual files as and batches of files from the web.

## Installing `wget`

In order to use `wget`, you'll need to install it: 

1. Follow the instructions in Step One of Ian Milligan's "Automated Downloading with Wget" tutorial
	- The tutorial instructions on how to download the `wget` command for Windows or Mac (if you're on a Mac, I recommend downloading via Homebrew)
2. Once you've downloaded `wget`, test that you have it running by entering the following command in your command line: `wget https://raw.githubusercontent.com/sceckert/IntroDHSpring2021/main/_week7/exploratory-data-analysis-with-pandas.ipynb` (this will download a copy of the Jupyter notebook from last class to your local machine)