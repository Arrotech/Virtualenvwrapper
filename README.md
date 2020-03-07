# Installing Virtualenv & Virtualenvwrapper

To install virtualenv and virtualenvwrapper run the following command on your terminal.

    pip install virtualenv virtualenvwrapper

You'll need to tell ZSH or BASH where virtualenvs need to be put. Below are the respective commands for both.
Assuming you are using vim editor just run:

For ZSH terminal;

    vim ~/.zshrc

For BASH terminal;

    vim .bash_profile

Press shift+I to add the next two lines to your .bash_profile or ~/.zshrc
To get your virtualenvwrapper path type `which virtualenvwrapper.sh` on your terminal and press enter.
Then add the following two lines.

    export WORKON_HOME=~/.virtualenvs
    source <virtualenvwrapper-path>

After adding both lines, press the esc key then `:wq` character keys to save and exit the .bash_profile.
Close and reopen your terminal when you’re done with all the steps above.

To create a virtual environment and activate it immediately, use the command below on your terminal:

Note that all your virtual environments would now live in the `~/.virtualenvs` folder.
Now you have virtualenv installed and a great wrapper around it.
Let’s explore it’s usage now. To create a virtual environment and activate it immediately, use the command below on your terminal:

    mkvirtualenv venv-wrapper

If you created your project folder already, you could cd into the folder before running the mkvirtualenv command with some arguments to automatically navigate to the project folder whenever you activate the virtual environment.
Here is the format: `mkvirtualenv [-a project_path] [-i package] [-r requirements_file] [virtualenv options] [env-name]`

    mkvirtualenv -a $(pwd) venv-wrapper

or

    mkvirtualenv -a $(pwd) python=python3 venv-wrapper

If you created your python environment first and made some module installations before creating your project folder and files e.g Django projects, no worries, you are not excluded in the goodies that come with automatically navigating to your project folder when you activate your virtualenv; Just run this command in the format- `setvirtualenvproject [~/.virtualenvs/your-virtual-env/] [~/path/to/your/project]`

    setvirtualenvproject ~/.virtualenvs/venv-wrapper/ ~/path/to/project/rootdirectory

Use the `deactivate` command to deactivate a virtual environment. Use the `workon env-name` command to subsequently activate a virtual environment or just run `workon` to list all available virtual environments created.
You can navigate to other created virtual environments while on a given environment without necessarily deactivating it first.

    workon venv-wrapper
    workon

You could use the `rmvirtualenv env-name` to remove an installed virtual environment.
Note that you must deactivate the virtual environment to be able to delete or remove it.

    rmvirtualenv venv-wrapper

There is this sweet command to copy an entire virtual environment to a newly created virtual environment.
If you haven’t felt the need to do this, you certainly would someday.
A typical scenario is when you need to observe the effect of meddling with specific modules in your current environment while preserving its original form.
Here is the command to copy your virtualenv: `cpvirtualenv [env-name] [target-env-name]`

    cpvirtualenv venv-wrapper copiedenv


### cdvirtualenv


Change the current working directory to `$VIRTUAL_ENV`.

Syntax:

    cdvirtualenv [subdir]

Calling `cdvirtualenv` changes the current working directory to the top of the virtualenv ($VIRTUAL_ENV).
An optional argument is appended to the path, allowing navigation directly into a subdirectory.