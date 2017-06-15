This is the README for the MWW API documentation (using Slate).

The documentation is deployed online at:

https://mwwondemand.github.io/


MWW API Documentation (using Slate)
------------------------------

With Slate,
 * **Description** - a description of your API is shown on the left side of your documentation, and
 * **Code** - all of your code examples are on the right side.


Getting Started with Slate Documentation
------------------------------

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 1.9.3 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

#### Getting Set Up

1. Fork this repository on Github.
2. Clone *your forked repository* (not our original one) to your hard drive using `git clone [repository name]`
3. `cd` into the new folder
4. Initialize and start Slate. You can either do this locally, or with Vagrant (if you have it installed):

```shell
# either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up
```

You can now see the docs at http://localhost:4567.

Now that Slate is all set up your machine, you'll probably want to learn more about [editing Slate markdown](https://github.com/tripit/slate/wiki/Markdown-Syntax), or [how to publish your docs](https://github.com/tripit/slate/wiki/Deploying-Slate).


Working on this repository
------------------------------

At present, the sections are:

* **Introduction** — blah
* **Authentication** — blah
* **Orders** — blah
* **Line Items** — blah
* **Web Hooks** — blah
* **Errors** — blah
* **Credits** — blah

How to make changes:

* Make changes on your fork and commit.
* Run `./build.sh`.
* Create a Pull Request on to **upstream** `master` from your **origin** `master`.

<!--
a comment
-->
