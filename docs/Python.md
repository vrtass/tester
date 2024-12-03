[&#x213C;](#)<br id="idx006">
## Check Python, Pip, and Venv

```
python --version
pip --version
python -m venv --help

```

[&#x213C;](#)<br id="idx007">
## Python Virtual Environment

```
# A centralized ".virtualenvs/" directory
mkdir -pv ~/.virtualenvs/

# Create a Virtual Environment
python3 -m venv ~/.virtualenvs/

```

[&#x213C;](#)<br id="idx008">
## Activate the Virtual Environment
* Before working with "MkDocs", always activate the virtual environment!

```
source ~/.virtualenvs/bin/activate

```

[&#x213C;](#)<br id="idx009">
## Install MkDocs and additional MkDocs plugins

* Upgrade, Clean Up, and Verify Version

```
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

[&#x213C;](#)<br id="idx010">
## MkDocs inside REPO

```
# You must be inside the git REPO.
mkdocs new .

```

[&#x213C;](#)<br id="idx011">
## File: mkdocs.yml 

```
copyright: Copyright &copy; 2024-2024 VRTASS
site_name: MkDocs Tester for Debian on VirtualBox
site_url:  https://vrtass.github.io/tester/
nav:
  - Home:  index.md
  - Page1: page1.md
  - Page2: page2.md
  - About: about.md
theme:
  name:    material
  font:
    text:  Merriweather Sans
    code:  Red Hat Mono
  logo:    assets/logo.jpg
  favicon: assets/favicon.ico
  features:
    - navigation.footer
  palette:
    # Dark Mode
    - scheme: slate
      toggle:
        icon: material/weather-sunny
        name: Dark mode
      primary: green
      accent: deep purple

    # Light Mode
    - scheme: default
      toggle:
        icon: material/weather-night
        name: Light mode
      primary: blue
      accent: deep orange

markdown_extensions:
  - attr_list
  - pymdownx.emoji:
      emoji_index: !!python/name:material.extensions.emoji.twemoji
      emoji_generator: !!python/name:material.extensions.emoji.to_svg
  - pymdownx.highlight:
      anchor_linenums: true
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
  - pymdownx.tabbed:
      alternate_style: true
  - admonition
  - pymdownx.details

extra:
  social:
    - icon: simple/youtube
      link: https://youtube.com/
    - icon: simple/linkedin
      link: https://linkedin.com/

plugins:
  - include-markdown
  - awesome-pages
  - macro

# REVISI: Tue 03 Dec 2024 13:00
# REVISI: Tue 03 Dec 2024 12:00
# REVISI: Tue 03 Dec 2024 11:00
# REVISI: Tue 03 Dec 2024 10:00
# STARTX: Tue 03 Dec 2024 09:00

```

* File about.md

```
echo "# About" > docs/about.md

```

* Assets: docs/assets/{favicon.ico,logo.jpg}
 
[&#x213C;](#)<br id="idx012">
## Test from VirtualBox

* Check it out at "localhost:4999" (HOST)

```
mkdocs serve --dev-addr=0.0.0.0:8000

```

[&#x213C;](#)<br id="idx013">
## Build the MkDocs site
* Build, commit, and push (master)

```
git add .
git commit -m "Save uncommitted changes"
git push

```

[&#x213C;](#)<br id="idx014">
## Deploy

```
mkdocs gh-deploy --force --clean
git checkout gh-pages
mkdocs serve --dev-addr=0.0.0.0:8000

```

* Checkit out at <https://vrtass.github.io/tester/>, but your are not VRTASS!

<hr>

```
REVISI: Tue 03 Dec 2024 16:00
REVISI: Tue 03 Dec 2024 11:00
REVISI: Sun 01 Dec 2024 22:00
REVISI: Fri 29 Nov 2024 19:02
REVISI: Fri 29 Nov 2024 18:00
STARTX: Tue 26 Nov 2024 12:00
```

