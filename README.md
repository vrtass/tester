# 251docs by BinKadal, Sdn, Bhd.

[&#x213C;](#idxXXX)<br id="idx000">
## Table of Content (Toc)
* [Network Address Translation (NAT) Settings](#idx001)
  * [VirtualBox](#idx001)
  * [UTM](#idx001a)
* [GitHub Repo 251docs](#idx002a)
  * [File .gitignore](#idx002)
* [Debian Packages](#idx003)
* [Check Python, Pip, and Venv](#idx004)

[&#x213C;](#)<br id="idx001">
## Network Address Translation (NAT) Settings

### VirtualBox

MkDocs is using local port 8000. 
On your VirtualBox, you must redirect/translate the local port 8000 to the host port 4999.
I am already using 5000 for Jekyll and 5001 for Docusaurus.

* VirtualBox Settings
  * Network:Adapter1:
    * Enable Network Adapter
    * Attached to: NAT
    * Port Forwarding:
      * 127.0.0.1:4999 (Host) --- 10.0.2.15:8000 (Guest)

<br><img src="images/VBOX-NAT.jpg"  width="960"><br>

[&#x213C;](#)<br id="idx001a">

### UTM

MkDocs is using local port 8000. 
On your UTM, you must redirect/translate the local port 8000 to the host port 4999.
I am already using 5000 for Jekyll and 5001 for Docusaurus.

* UTM Settings
  * Network Mode: Emulated VLAN
    * Port Forward: New
      * Protocol: TCP
      * Guest Address: 10.0.2.15
      * Guest Port: 8000
      * Host Address: 127.0.0.1
      * Host Port: 4999
   * SAVE

<br><img src="images/debM1-forward.jpg"  width="960"><br>

[&#x213C;](#)<br id="idx002a">
## GitHub Repo 251docs

* Create a new [GitHub](https://github.com/) repo.
  * New Repository
  * Repository Name: "251docs"
  * Description: "251docs"
  * Public
  * Add README.md
  * Add .gitignore: Python (temporary)
  * Choose any free LICENSE
  * See also <https://doit.vlsm.org/030.html>
* Create a GitHub page.
  * (Create branch: gh-pages), apparently will automatically create a GitHub Page?!
  * See also <https://doit.vlsm.org/031.html>
* CLONE Your GitHub Repo on VirtualBox. E.g.

```
git clone git@github.com:cbkadal/251docs.git

```
* REMEMBER: You are not **CBKADAL**!
* Write your memo on file "README.md".
  * Update/push "README.md" regularly.

[&#x213C;](#)<br id="idx002">
### File .gitignore

Copy the following into your .gitignore file:
https://raw.githubusercontent.com/cbkadal/251docs/master/.gitignore

[&#x213C;](#)<br id="idx003">
## Debian Packages (root)

Make sure the following Debian packages are present in your system.

```
# USER privilege.
export DEBS="
aptitude
build-essential
git
libffi-dev
libssl-dev
python3
python3-dev
python3-pip
python3-venv
sudo
vim
"
date;
sudo apt-get install $DEBS -y

```

[&#x213C;](#)<br id="idx004">
## Check Python, Pip, and Venv

```
python --version
pip --version
python -m venv --help

```



### XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX




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





<hr>

```
REVISI: Thu 28 Nov 2024 22:00
REVISI: Tue 26 Nov 2024 18:00
STARTX: Tue 26 Nov 2024 12:00
```

