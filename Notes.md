####Essential dev tools####

Great Resource: https://www.datacamp.com/community/tutorials/python-developer-set-up

#vscode extensions
Python extension by microsoft

#linter
pylint (included in python vscode extension)

#type checker
mypy -> static type checker (ides like PyCharm will have this build in tho, not Vscode as of now)
need to import typings for List, Set, Dict, Tuple, Optional, Callable, Iterator, Union (and more)
so like this:
from typing import List, Set, Dict, Tuple, Optional
refer to https://mypy.readthedocs.io/en/latest/cheat_sheet_py3.html

#formatter
formatter: popular are autopep8, black and yapf
these are all built into python extension in vscode and you can switch between these
WINNER: black, due to being opinionated and non configurable

#package manager
pip -> python package manager, equivalent to npm
pip freeze -> List installed packages
pip freeze > requirements.txt -> Put installed packages in a requirements file (all deps, this is similar to package.json)
pip install -r requirements.txt	-> Install packages listed in the given requirements.txt file
check in requirements.txt to git repo
great tool to use is pip-autoremove to remove a package and all its dependencies (without this, pip uninstall just removes the package itself without removing deps)

#virtual environment
venv -> python virtual env
create with this command:
py -m venv MYVENVNAME
(good name for MYVENVNAME is .venv, makes it obvious that its a settings dir)
then to activate venv, run Activate.ps1 (or equivalent in the scripts(maybe its called bin on linux/mac) folder)
if you did this right, you should have a (.venv) in the command line cursor, and when you first create this, 
when you call pip freeze there should be nothing there (cause no deps have been installed)
from here you can install packages in isolation from other projects, or download a project's "requirements.txt" to quickly install all the deps (like npm install)
don't check this dir into git 
BUG: https://stackoverflow.com/questions/55380296/how-to-fix-error-errno-2-no-such-file-or-directory-c-program-files-pytho
if missing debugger tools, follow steps in link above
more info refer to docs here: https://docs.python.org/3/library/venv.html, https://www.datacamp.com/community/tutorials/python-developer-set-up (latter has full walkthru)
to deactivate a venv, just type deactivate in shell. The green (.venv) should go away. This is good for switching envs when switching projects, or for example if you want to upgrade pip globally (or other packages)