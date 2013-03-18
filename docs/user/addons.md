---
title: Build Addons
layout: en
permalink: addons/
---

<div id="toc"></div>

## Addons

Travis CI allows you to set up some build tools using settings right in your
.travis.yml file.

Currently, the only available addon is [Sauce Connect][sauce-connect].

[sauce-connect]: https://saucelabs.com/docs/connect

### Sauce Connect

[Sauce Connect][sauce-connect] securely proxies browser traffic between Sauce
Labs' cloud-based VMs and your local servers. Connect uses ports 443 and 80 for
communication with Sauce's cloud. If you're using Sauce Labs for your Selenium
tests, this makes connecting to your webserver a lot easier.

First, [sign up][sauce-sign-up] with Sauce Labs if you haven't already (it's
[free][open-sauce] for Open Source projects), and get your access key from your
[account page][sauce-account]. Once you have that, add this to your .travis.yml
file:

    addons:
      sauce_connect:
        username: "Your Sauce Labs username"
        access_key: "Your Sauce Labs access key"

[sauce-sign-up]: https://saucelabs.com/signup/plan/free
[sauce-account]: https://saucelabs.com/account
[open-sauce]: https://saucelabs.com/signup/plan/OSS

If you don't want your access key publicly available in your repository, you
can encrypt it with `travis encrypt "your-access-key"` (see [Encryption Keys][encryption-keys]
for more information on encryption), and add the secure string as such:

    addons:
      sauce_connect:
        username: "Your Sauce Labs username"
        access_key:
          secure: "The secure string output by `travis encrypt`"

[encryption-keys]: http://about.travis-ci.org/docs/user/encryption-keys/
