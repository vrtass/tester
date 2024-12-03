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
tree
vim
wget
"
time sudo apt-get install $DEBS -y
date

```

!!! note "Revision:"
    <pre>
    REVISI: Tue 03 Dec 2024 23:00
    STARTX: Tue 03 Dec 2024 21:00
    </pre>

