---
---
```
REVISI: Thu 28 Nov 2024 20:01
REVISI: Tue 26 Nov 2024 18:00
STARTX: Tue 26 Nov 2024 12:00
```

sudo apt install -y \
  build-essential libffi-dev libssl-dev python3 python3-dev python3-pip python3-venv

python --version
pip --version
python -m venv --help

# CREATE AND CLONE REPO
git clone REPO

# A centralized ".virtualenvs/" directory
mkdir -pv ~/.virtualenvs/

# Create a virtual environment
python3 -m venv ~/.virtualenvs/$(basename $(pwd))

# Activate the virtual environment
source ~/.virtualenvs/$(basename $(pwd))/bin/activate

# Upgrading the virtual environment’s pip
~/.virtualenvs/$(basename $(pwd))/bin/python -m pip install --upgrade pip

# Check the version
pip --version

# install MkDocs and additional MkDocs plugins
pip install mkdocs mkdocs-material

# Clean UP
pip cache purge

# Verify Version
mkdocs --version

# Create a docs/ Directory
mkdir -pv docs/
cd docs/
mkdocs new .

# Test from VirtualBox
mkdocs serve --dev-addr=0.0.0.0:8000

# Build the MkDocs site
mkdocs build

# Create and switch to a clean gh-pages branch for the first time
git checkout --orphan gh-pages

# Switch to a clean gh-pages branch
git checkout gh-pages


# Remove all files from the gh-pages branch:
git rm -rf .
cp -rv site/* ../
cd ../
git rm -rf docs/
git add .
git commit -m "Deploy MkDocs site"
git push origin gh-pages






