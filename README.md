The Open Health Care Developer Toolkit aims to provide a standard development environment for all OHC projects.

(It's a Vagrant box with everything you need set up for you!)

## Installation

OK, that sounds neat - what do I do now?

### Step 0. - Prerequisistes

You should  have the following things installed: 

* Virtualbox (https://www.virtualbox.org/)
* Vagrant (http://www.vagrantup.com/)
* Python (https://www.python.org/)
* Virtualenv[Wrapper] (http://virtualenvwrapper.readthedocs.org/en/latest/)

Got all that? Proceed directly to step 1.

### Step 1. - Bootstrapping

Clone this repository: 

    $ git clone git@github.com:openhealthcare/developer ohcdev

Create yourself a virtualenv for the dev environment: 

    $ cd ohcdev
    $ mkvirtualenv -a $PWD ohcdev

Install the requirements for provisioning your dev environment: 

    $ pip install -r requirements.txt

Run the bootstrap script: 

    $ ./bin/bootstrap

### Step 2. - 

TODO: Create a superuser
TODO: Run the service(s)
TODO: Run the tests

### Step 3. 

There is no step 3. 