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

### Step 0. - Preparation

You should make sure that you've set up SSH agent forwarding!
If you've not done this before, running ssh-add will help.

    $ ssh-add

### Step 1. - Bootstrapping

Clone this repository: 

    $ git clone git@github.com:openhealthcare/developer ohcdev

Create yourself a virtualenv for the dev environment: 

    $ cd ohcdev
    $ mkvirtualenv -a $PWD ohcdev

Install the requirements for provisioning your dev environment: 

    $ pip install -r requirements.txt

Edit the vagrant provisioning config at `./provision/vagrant.yml` `to enable the components you
want to install.

Run the bootstrap script: 

    $ ./bin/bootstrap

```Note: if you're running an old version of Vagrant (< 1.6.3), it may not know about the existence of 
named boxes on Vagrant Cloud. Try updating the latest version!```


```Note: if something fails and you want to re-run the provisioner, try vagrant provision```

### Step 2. - Run Something

OK - so the bootstrap script will have created you a VM, installed some development tools onto it, checked out the source code of out projects, installed dependencies, created users, and generally done a whole bunch of lifting for you.

Next step is to log into the VM: 

    $ vagrant ssh

From there you will have some virtual environments for projects set up - activate one of these: 

    $ workon elcid

This will activate the correct sandbox and take you to the correct working directory for that project. 

From here , you can run the service: 

    $ python manage.py runserver 0.0.0.0:8000

The vagrant box will forward this port - so you should be able to now visit http://localhost:8000 and see a running version of the project. 

Standard development superusers will have been created, so try logging in with super/super1

### Step 3. 

There is no step 3. 

## What now?

This process has created a stable, automated development environment for you!

The source code for projects is located in /usr/lib/ohc/... in the vagrant box, which is mounted to ./src on your guest. 

More specific documentation about each individual project should be available from it's source code or documentation site.

## Other Documents

* [Development Workflow](../DevelopmentWorkflow.md)
* [Release Process](../ReleaseProcess.md)
