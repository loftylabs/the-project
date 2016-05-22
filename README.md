# The Project

## Introduction

`The Project` is a self-guided application project for all prospective Lofty consultants. We believe that an engineer's merit is not always described by their resumé. Sometimes a great engineer hasn't had an opportunity to prove themselves yet or maybe they're just uncomfortable in interviews and don't end up giving their true ability the chance to shine in an stressful interview. `The Project` helps us determine a potential consultant's true ability outside of the black and white confines of their resumé and sometimes those awkward face-to-face interviews.

`The Project` will explore your capability as a Python developer using our preferred tooling. We don't expect all applicants to have proficiency in all of the technologies specified in this document.  Lofty Labs Consultants often work independently with only a small amount of direct supervision and often work directly on projects built by other engineering teams as well. Sometimes this introduces new systems to us that we haven't used before. This project is meant to expose you to the same situation wherein maybe you haven't used all of the technologies or tooling that we have specified in the requirements. Completion of `The Project` will show that even if you don't have experience with all of the specifications listed, you're a dedicated and passionate engineer that is able to pick up new systems and technologies at an at least basic level. The ability to adapt to a new and possibly unknown technology is a core competency of all Lofty Engineering Consultants.

## Getting Help

While working on this project, you will have access to members of the Lofty Labs consulting team via Slack. Contact us at `jobs@hirelofty.com` and let us know you'd like to be a part of the project and we'll add you to our slack channel named `#the-academy`. If you get stuck, or even just want to discuss the project in general, you are encouraged to ask questions and get help from the Lofty Engineering team as well as the other potential consultants working on the same project as you. A key component of the value we add to our client's projects as a consultantcy is our ability to communicate across many disparate teams and utilize everyone’s particular areas of expertise. Our clients don't hire us because we know every solution off-hand; our client's hire Lofty Labs because we know how to solve problems. Solving our client's problems includes research, continuing education, and cross-team knowledge sharing. What this means for you as a potential consultant working on `The Project` is that we don't mind you asking questions throughout your progress in slack. We don't care that you ask questions. We care that you ask *the right* questions.

## Description

`The Project` requires you to build an analytics dashboard using Twitter data. The application should show usage information for a particular hashtag of your choosing and it should periodically retrieve data from Twitter’s API and store the results. The application should be interactive and highly performant. Since user's will be interacting with data cached in your application as opposed to pulled on request from Twitter, the application should be very performant and allow for smooth interactivity with the user.

For the hashtag you choose, the dashboard should show:

* A date histogram of hashtag usage, by hour, for the previous 7 days
* Most retweeted tweet, by day, for the previous 7 days
* Some other metric of your choosing, that you found interesting when exploring the data.

## Full Project Specification

### Backend stack

The server application needs to be written in `Python 3` using `Django 1.9`. Data should be retrieved asynchronously using `Celery` on an interval scheduled with `Celerybeat`. For this project, Django can serve as both the Celery Broker and result backend.

Data retrieved from Twitter should be stored using the Django ORM in a `PostgreSQL` database, and should be served up to the UI via a RESTful API built with `Django Rest Framework`.

### UI Stack

The UI should be a modern and standards compliant web application using `Bootstrap 3` as a CSS framework. You have the option to choose whichever Javascript framework you prefer to build the application. You will get bonus points for using `React.js` or `EmberJS`

Data visualizations can be implemented using `Flot`, `d3.js` (including derivatives like `NVD3`), or `Chart.js`. Front-end build systems are entirely optional, but we’ve been enjoying `webpack` lately.

### Functionality

The UI application should require basic authentication (a username and password) and have the ability to create new user accounts on demand. Django’s built-in authentication system is fine, so long as it is configured to work with `Django Rest Framework` correctly.

Twitter data should be stored in a single model/database table. The schema is up to you, but aggregations should happen at runtime either at the database level or in Python if you can optimize the performance well enough.

The application should consist of three views. These views can be implemented as an SPA (Single Page Application) in JavaScript or as three separate `Django` views. There is no penalty or benefit to choosing one or the other.

* Login view

  Unauthenticated users are directed here

* Dashboard view

  Authenticated users are directed here and can view the dashboard

* User management view

  User account CRUD happens here.

All data interaction with the backend should occur over the REST API

### Workflow & Infrastructure

To get started on `The Project`, fork this respository on GitHub and do all work inside that forked respository.

The application (`Django` and `Celery`) should be deployed to an `Amazon EC2` server. A `t2.micro` instance will be more than adequate. The instance should run Ubuntu 14.04 and the database should be deployed to Amazon RDS. You should be able to create all of these instances on Amazon Web Service's free tier at no cost to you.

`Django` should be deployed using `uWSGI`, which should be running behind `Nginx` via a reverse proxy.

### Get Started!

Good luck, and be sure to check the resources section below for further reading materials!

### Resources

In addition to the Lofty Labs Slack channel, here are some good places to start when researching the various tools needed to build this application.

* [Very good beginner's Python reference](http://learnpythonthehardway.org/book/)
* [Django tutorial](https://docs.djangoproject.com/en/1.9/intro/tutorial01/)
* [Django Rest Framework (for building an API)](http://www.django-rest-framework.org/)
* [Celery with Django](http://celery.readthedocs.org/en/latest/django/first-steps-with-django.html)
* [Celerybeat](http://celery.readthedocs.org/en/latest/userguide/periodic-tasks.html)
* [Twitter Bootstrap CSS framework](http://getbootstrap.com/)
* [jQuery](http://learn.jquery.com/)
* [Amazon EC2 Documentation](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html)
* [Amazon RDS Documentation](https://aws.amazon.com/documentation/rds/)
* [Git tutorial](http://www.git-scm.com/book/en/v1/Getting-Started)
* [GitHub Documentation](https://help.github.com/)
* [DRY (Don't Repeat Yourself)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
