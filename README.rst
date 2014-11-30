21strun's Django Reusable App Template
======================================

This repository is a fork of `bitmazk/django-reusable-app-template 
<https://github.com/bitmazk/django-reusable-app-template>`_ aims to help you to kickstart new reusable Django apps
customized for 21strun company purposes within a few minutes.

In order to kickstart your new reusable app customized for 21strun, just do the following

.. code-block:: bash

    git clone git://github.com/21strun/django-reusable-app-template.git your-app-name
    cd your-app-name
    nano init.sh
    # change all variables to your needs
    ./init.sh

The init script will replace all placeholders in the project files in the
``template`` folder with your desired values. Then it will rename a few
folders into your desired app name. Next it will remove the ``.git`` folder,
move everything from ``template`` into the root folder and create a first
initial commit. Now you have a new reusable app that does nothing, yet.

After this you can create the virtual environment or your app

.. code-block:: bash

    mkvirtualenv -p python2.7 your-app-name
    python setup.py install
    pip install -r test_requirements.txt

Now you can run the tests

.. code-block:: bash

    ./your-app-name/tests/runtests.py

Or you can initiate the database and preview your app in the browser

.. code-block:: bash

    ./manage.py syncdb --all
    ./manage.py migrate --fake
    ./manage.py runserver

The only URL that is hooked up will be the admin url, so you can open
`localhost:8000/admin/`.

Once you have implemented your app, you may publish it on the Python Package
Index like so - this step is **only for apps that should be published!**

.. code-block:: bash

    python setup.py register
    python setup.py sdist upload
