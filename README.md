# Django Init Project

Project template forked on [django-init](https://github.com/Fueled/django-init) for create django projects, optimized for making REST API with deployment on Heroku and EC2 instances via Ansible.

## Requirements

* Python 3.6.x
* Docker
* Docker Compose

## Features

* Django 2.0.x
* Python 3.6.x
* [12-Factor][12factor] based settings management via [django-environ], reads settings from `.env` if present.
* PostresSQL everywhere
* PostGIS support (optional)
* Docker Compose for development (Database, Redis, etc)
* Ready to deploy on Heroku (optional) and Ubuntu 16 LTS via [Ansible](Optional)
* [Django Rest Framework][drf] 3.7.x. ready.
* Uses `django_sites` instead of `django.contrib.sites`
* Use [mkdocs] for project documentation.
* Uses [pytest] as test runner.
* Config files for running isolated tests and deployments to dev/qa/prod environment on Heroku from git branches.
  * Jenkins: `Jenkinsfile`
  * Circle CI: `circle.yml`
  * Travis: `travis.yml`
* Custom `User` app, for easier extensibility.
* Media storage using Amazon S3 (optional)
* [Letsencrypt](https://letsencrypt.org/) Support via [certbot](https://certbot.eff.org)
* SASS with autoprefixing support using django-compressor (optional)
* Livereloading of browser in development via [devrecargar]
* robots.txt and humans.txt configured

## Getting Started

Install cookiecutter with `brew install cookiecutter` or `pip install cookiecutter`.

```
cookiecutter gh:condadolabs/init-project
```

It will ask you couple of questions required to generate the project. It will generate a folder containing all the files in your current working directory.

If you opt to setup the project automatically, it will also:

* initialize a git repo and bump initial tag and version.
* create a virtualenv in the folder `venv` inside the project.
* install all the python dependencies inside it.
* try to create a postgres database and run the initial migration against it, using your container via `docker-compose`.

then only thing you'll need to do is:

1.  `cd` into the new `github_repository` folder just created.
2.  Activate virtualenv `source venv/bin/activate`.
3.  Run `fab serve` or `./manage.py runserver`

Don't forget to carefully look at the generated README. Awesome, right?

You can also explore the [wiki] section for details on advance setup and usages. (SOON)

## Release Policy

`init-project` is a rolling release project. Commit and fixes are added to `master` branch on regular basis and always have latest stable django and associated libraries. You are advised to follow-up with changelogs.

## Changelogs

Refer to [CHANGELOG.md](CHANGELOG.md).

## Code of Conduct

Everyone interacting in the django-init project's codebases, issue trackers, chat rooms, and mailing lists is expected to follow the [PyPA Code of Conduct](https://www.pypa.io/en/latest/code-of-conduct/).

## Related Projects

* https://github.com/Fueled/django-init
* https://github.com/pydanny/cookiecutter-django
* https://github.com/wemake-services/wemake-django-template
* https://github.com/lionheart/django-template

---

Thinks for the [Fueled](https://fueled.com) for creating this template.

[wiki]: https://github.com/condadolabs/init-project/wiki
[mkdocs]: http://www.mkdocs.org/
[12factor]: http://12factor.net
[pytest]: http://pytest.org/
[django-environ]: https://github.com/joke2k/django-environ
[ansible]: http://docs.ansible.com/index.html
[devrecargar]: https://github.com/scottwoodall/django-devrecargar
[drf]: http://www.django-rest-framework.org/
