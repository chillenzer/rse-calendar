# RSE Calendar project

This repository contains code for building a Jekyll site that shows upcoming
events and builds and hosts .ics calendar files of those events that can be
subscribed to. It was built with the idea of providing a central website
containing research software engineering events in the UK that can be
contributed to easily.

## Contributing an event to the calendar

To add an event to the calendar you should suggest a [pull
request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request?tool=webui)
to the repository that updated the [main data file](./_data/main.yaml) to add a new
event to the events section with the following YAML format:

```yaml
  - summary: title of your event
    description: |
      A description of your event that can be
      over many lines
      With URLs wrapped in <www.example.com> 
    location: A location (virtual or in real life)
    begin: YYYY-mm-DD HH:MM:SS
    # duration should contain a unit of time: minute, day, hour 
    # and an numeric value
    duration: { minutes: 45 }
    event_url: www.example.com
```

> **Note**
> To ensure any extra URLs or email address in the description field are
> clickable, wrap them in angle brackets to allow the
> [Kramdown
> processor](https://kramdown.gettalong.org/syntax.html#automatic-links) to
> properly convert them into anchor elements.

We'll do our best to get to your pull request and merge it so your event is
shown on the website and in the calendar feed.

## Contributing to the site

First, thank you for wanting to contribute! We're very happy to review and
accept contributions from others to improve this site.

To get started you should:

1. Make a [fork](https://github.com/Sparrow0hawk/git-calendar-test/fork) of this
   repository
2. Clone your fork locally
3. To run the site locally you will need:
    -  Ruby 2.7, I'd recommend installing this via
       [rvm](https://github.com/rvm/rvm)
    - Python 3
4. Once Ruby is installed you can install the required Ruby Gems with `bundle
   install`
5. To run the Python steps locally you will need to install the required
   packages. I'd recommend doing this with the following steps:
   1. Create a virtual environment `python -m venv venv`
   2. Activate the virtual environment `source venv/bin/activate`
   3. Install the dependencies into the virtual environment `pip install -r
      requirements.txt` 
6. With Python setup steps completed to you can do the following steps to
   generate the calendar files and to generate posts from the main data file
7. To create the calendar files: `./build.sh` will run the git-calendar tool
8. To create posts from the data file: `python _scripts/generate_posts.py`
9. Now you've done all the prep you can run the site locally using `bundler exec
   jekyll serve`

## Acknowledgements

This projects builds on:

- The coderefinery [git-calendar tool](https://github.com/coderefinery/git-calendar-template)
- Themes from [Jekyll minima](https://github.com/jekyll/minima)
