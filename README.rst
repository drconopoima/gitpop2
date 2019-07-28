GitPop2
==============

Find the most popular fork on GitHub <http://gitpop2.herokuapp.com/>
--------------

GitPop2 helps you choose a fork when a project goes unmaintained. It allows you to sort forks by "stars count", "forks count" and "last update".

![Screenshot](https://raw.github.com/AndreMiras/gitpop2/master/docs/screenshot.png)


Install using Pipenv
--------------

This project uses Pipenv as packaging tool, and is currently only compatible with Python 2.7.16. 

.. code::sh
    pipenv install


Install with Pip and Pyenv
-----------

If you prefer to install by using pip, use the following steps:

It's recommended that you set up a virtual environment with [latest python 2 version](https://www.python.org/downloads/).

.. code::sh
    pyenv install 2.7.16 [...--verbose]

Then create a virtual environment:

.. code::sh
    pyenv virtualenv 2.7.16 gitpop2-2-7-16

If you use gitpop2-2-7-16 as the name, the required .python-version_ file to enable your virtual environment upon entering the folder is already in the repo.

.. code::sh
    pyenv activate gitpop2-2-7-16

Then install the requirements:

.. code::sh
    python -m pip install -r requirements.txt


Install Pipenv
-----------

.. code::sh
    pip3 install --user pipenv

Then you need to add the pipenv location to your PATH:

.. code::sh
    echo "export PATH=\$HOME/.local/bin:\$PATH" >> ~/.profile && source ~/.profile

You could be using a different file for the profile of your shell in your system, e.g. .bash_profile_ or .zprofile_. I recommend that you place it in one of these files for your specific shell instead of using .profile_.

You can shell into the virtualenv by using:

.. code::sh
    pipenv shell

You can run a file using the virtualenv with:

.. code::sh
    pipenv run

If you prefer to remove the virtualenv:

.. code::sh
    pipenv --rm


Install Pyenv
-----------

You may not have Python 2.7.16 installed in your system, as it's approaching EOL in January 2020. You would need to use Pyenv to install it locally for your user.

Using [Pyenv-installer](https://github.com/pyenv/pyenv-installer). Please refer to the official project page to review the up-to-date install instructions. As of now, you would run:

.. code::sh
    curl https://pyenv.run | bash

As Pyenv compiles the version of python from source, it has certain build dependencies. Please refer to the project's [Common build problems](https://github.com/pyenv/pyenv/wiki/common-build-problems) and preemptively install dependencies for your system.

Then you would need to add certain variables to your path. Add the following files to either your .bashrc_, .zshrc_, .bash_profile_ or .zprofile_.

.. code:sh
    export PATH="$HOME/.pyenv/bin:$PATH"
    eval "$(pyenv init -)"
    eval "$(pyenv virtualenv-init -)"

You can choose to add these lines by using the following command:

.. code:sh
    export SHFILE=".profile" && echo "export PATH=\"\$HOME/.pyenv/bin:\$PATH\"" >> $SHFILE && echo "eval \"\$(pyenv init -)\"" >> $SHFILE && echo "eval \"\$(pyenv virtualenv-init -)\"" >> $SHFILE && source ~/.profile

Run
--------------
With Gunicorn WSGI server:

.. code::sh
    gunicorn gitpop2.wsgi

With Django development server:

.. code::sh
    python manage.py runserver


TODO
--------

Upgrade package to be compatible with Python 3.


Credits
-------

This package is forked from [AndreMiras/gitpop2](https://github.com/AndreMiras/gitpop2) project.

This project actually started as a "fork" of [jpmckinney/gitpop](https://github.com/jpmckinney/gitpop), because the site running the project went down in March 2014.
It's not a fork as defined by GitHub because it was started from scratch using a different web framework.