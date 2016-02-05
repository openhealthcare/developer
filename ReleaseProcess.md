# Making a release

This document outlines the process of making a release of an Open Health Care Project.

This is a living document that will change over time.

### Changelog

Ensure that the changelog is up to date with the contents of this release.

### Merge Checks

Create a Pull Request to merge the release branch into master. This should allow you to check (via continuous integration) that after your release all of our tests and quality checks still pass. Assuming that they do, merge the PR.

### Tagging

Tag the release appropriately in git.

### Github Release pages

Update the Github release pages to include details of this release.

### Update documentation

If this project has an external documentation website, make sure that it is updated with the latest version.

### Package Repositories

If this project is published on an external packaging system (e.g. PyPi) then upload the release to that system.

### Blog post

Now that we've done the hard work, it's time to tell the world what we've been up to. Write a blog post and publish it.
