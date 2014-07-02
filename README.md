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

Note: You should make sure that you've set up SSH agent forwarding!
If you've not done this before, running ssh-add will help.

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

### Step 2. - Run Something

OK - so the bootstrap script will have created you a VM, installed some development tools onto it, checked out the source code of out projects, installed dependencies, created users, and generally done a whole bunch of lifting for you.

Next step is to log into the VM: 

    $ vagrant ssh

From there you will have some virtual environments for projects set up - activate one of these: 

    $ workon elcid

This will activate the correct sandbox and take you to the correct working directory for that project. Before you start, you should create yourself a superuser account:

    $ python manage.py createsuperuser

After you've created yourself a user , you can run the service: 

    $ python manage.py runserver 0.0.0.0:8000

The vagrant box will forward this port - so you should be able to now visit http://localhost:8000 and see a running version of the project. 


TODO: Run the tests

### Step 3. 

There is no step 3. 

## What now?

This process has created a stable, automated development environment for you!

The source code for projects is located in /usr/lib/ohc/... in the vagrant box, which is mounted to ./src on your guest. 

More specific documentation about each individual project should be available from it's source code or documentation site.

## Development Workflow

All projects are Code-In-The-Open, with governance conducted on public mailing lists and a record of issues/responses available on the web.

In practice, this means that we have a google group and a github repository.

The workflow for OHC projects is broadly as follows: 

### Issue

Issues are created on a public bug tracker, either by developers for technical issues, end users, or Some Other Interested Party

Issues are prioritised & assigned through a process that differs slightly from project to project, but follows some mutation of "Agile". 

c.f. [the elCID Waffle board](https://waffle.io/openhealthcare/elcid)

### Branch, Code & Tests

Work happens in a broadly branch-per-issue manner, except when it doesn't.

All new code && bugfixes should come with appropriate tests, except when they don't.

All new interfaces should come with appropriate documentation, except when they don't.

Use your skill, experience && judgement to figure out when the thing you're doing is exceptional ;)

### PR & Review

All code gets reviewed by a technical colleague where possible - so PRs are your friend. Exeptions may apply to "all". 


### Deploy to test 
As a general rule, we maintain test servers per deployment, and per sprint/major feature set, on some kind of cloud IAAS/PAAS system. Specifics will vary. 

### Sign-off

As a general rule the originator of the issue should sign off that the implementation meets their needs. In practice, use your skill & judgement. 

