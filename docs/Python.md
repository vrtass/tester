## Check Python, Pip, and Venv

What is the current version?

```
python --version
pip --version
python -m venv --help

```

## Python Virtual Environment

A Python virtual environment is used for dependency isolation, 
avoidance of global installation, management of different Python versions, 
simplified dependency management, cleaner development environment, 
version control compatibility, and security.

```
# A centralized ".virtualenvs/" directory
mkdir -pv ~/.virtualenvs/

# Create a Virtual Environment
python3 -m venv ~/.virtualenvs/

```

## Activate the Virtual Environment
* Before working with "MkDocs", always activate the virtual environment!

```
# Always activate the VENV
source ~/.virtualenvs/bin/activate
tree

```

Once activated, you should see the name of the virtual environment in your terminal prompt, i.e. 
**"(.virtualenvs) cbkadal@cbkadal:~/git/tester$ "**

![Virtual Environment](img/venv.jpg){ width=95% }


## Install MkDocs and additional MkDocs plugins

* Do not forget to activate the virtual environment!

```
# Upgrade, Clean Up, and Verify Version
pip install --upgrade          \
pip                            \
mkdocs                         \
mkdocs-awesome-pages-plugin    \
mkdocs-include-markdown-plugin \
mkdocs-macros-plugin           \
mkdocs-material                \
pymdown-extensions             \

echo "= ======================================="
pip --version
mkdocs --version
pip cache purge

```

```text
STARTX: Tue 03 Dec 2024 21:000
```

