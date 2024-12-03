# GitHub Repo Setting

I prefer to start from GitHub so the results can be cloned.

## New GitHub Repo (GitHub Site)

Create a new repo according to your respective faith and beliefs. 
I am using user "vrtass" and creating a new repo "tester" in this example.

* Create a new [GitHub](https://github.com/){:target="_blank"} repo.
    * New Repository
    * Repository Name: "tester"
    * Description: "tester"
    * Public
    * Add README.md
    * Add .gitignore: Python (temporary)
    * Choose any free LICENSE
    * See also <https://doit.vlsm.org/030.html>{:target="_blank"}
* Create a GitHub page.
    * There is no need to do anything since the branch "gh-pages" will automatically create a GitHub Page?!
    * See also <https://doit.vlsm.org/031.html>{:target="_blank"}

## Clone Repo on Your Debian

I am using user "vrtass" and creating a new repo "tester" in this example.
Remember, <span class="red-text">YOU ARE NOT VRTASS!</span>

```test
# You are not vrtass, replace this with your own repo!
GITHUB="vrtass"

```
```test
# You might want to use any other repo name!
REPO="tester"

```

```test
# Make sure, you have the proper GITHUB and REPO variable!
git clone git@github.com:$GITHUB/$REPO.git
cd $REPO/

```

## File .gitignore

Copy the following into your .gitignore file:

```yaml
{% include "configs/gitignore" %}

```

```text
STARTX: Tue 03 Dec 2024 18:00

```

