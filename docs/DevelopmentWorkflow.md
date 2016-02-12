## Development Workflow

This document outlines the Open Health Care development workflow.

All of our projects are Code-In-The-Open, with governance conducted on public mailing lists and a record of issues/responses available on the web.

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

Pull Requests should ask the following questions: 

* Do these changes meet the User Need?
* Does the code have appropriate documentation after this change is made?
* Are these changes appropriately tested?

### Deploy to test 
As a general rule, we maintain test servers per deployment, and per sprint/major feature set, on some kind of cloud IAAS/PAAS system. Specifics will vary. 

### Sign-off

As a general rule the originator of the issue should sign off that the implementation meets their needs. In practice, use your skill & judgement. 

