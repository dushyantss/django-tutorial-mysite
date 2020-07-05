# django-tutorial-mysite
djangoproject.com tutorial for mysite


## Dependency Management
We are using [pip-tools](https://github.com/jazzband/pip-tools) for dependency management. We use the [layered requirements approach](https://github.com/jazzband/pip-tools#workflow-for-layered-requirements). The steps are as follows:

* We have two requirement files, requirements.in and dev-requirements.in
* If we have a project dependency we use requirements.in, if we have a dev only dependency, we add it to dev-requirements.in.
* When we add a new dependency to requirements.in, we need to run `pip-compile`, if we add to dev-requirements.in, we need to run `pip-compile dev-requirements.in`.
* To install in production(no dev dependencies), use `pip-sync`. To install dev dependencies use `pip-sync requirements.txt dev-requirements.txt`.
* To update dependencies, use `pip-compile --upgrade`, if upgrading dev dependencies use `pip-compile --upgrade dev-requirements.in`.