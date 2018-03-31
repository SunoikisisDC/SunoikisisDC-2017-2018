# Installation notes

(tested to work on Unix systems. They will need to be slightly adapted to work on Windows).

## Setup

Make sure you have **Python 3** install on your machine.

To be sure run

```bash
python --version
```

It should output something starting with `3.x`.

Now install `pipenv` by typing:

```bash
pip install -U pipenv
```

## Create virtual environmet and install dependencies

Create a project directory:

```bash
mkdir ~/sunoikisis_9/
```

Put in this directory the following files:

- the [Jupyter notebook](https://github.com/SunoikisisDC/SunoikisisDC-2017-2018/blob/master/Session_9_PoSTagging_Lemmatization.ipynb)
- [`Pipfile`](./Pipfile) and [`Pipfile.lock`](./Pipfile.lock)

If you now run 

```bash
cd ~/sunoikisis_9/
pipenv install --dev
```

This will install all your dependencies into a new virtual environment (like a container for all your python dependencies that can be removed at any time, meaning the libraries are not installed globally on your system).

## Install `TreeTagger`

One last thing to do is to install the `TreeTagger` tool.

I've created an installation script to do this. That's how you can call it:

```bash
# on Mac OS you choose to install treetagger at /Applications/treetagger/
cd ~

# grab the install script with wget (but you can also use curl) or just
# download it manually into this folder
wget -O install_treetagger.sh https://raw.githubusercontent.com/mromanello/CitationExtractor/master/install_treetagger.sh

# make the script executable (essential!)
chmod a+x install_treetagger.sh

# run it
./install_treetagger.sh

# remove it when done
rm install_treetagger.sh
```

**NB:** If you're installing TT on a Linux machine, make sure you swap lines 6 and 7 of `install_treetagger.sh` (uncomment #7 and comment out #6).


To test:

```bash
echo "Here it is a sentece to PoS Tag" | cmd/tree-tagger-english
```

Now you're done and ready to do your exercise. Just start jupyter by typing (from within the same directory with Pipfile(s) and notebook):

```bash
jupyter notebook
```
