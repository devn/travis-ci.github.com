---
title: Introducing Addons
permalink: blog/2013-03-18-introducing-addons
created_at: Mon 18 Mar 2013 07:43:00 GMT
author: Henrik Hodne
twitter: henrikhodne
layout: post
---

If you've ever tried to do browser testing against multiple browsers before,
you know how much of a pain it can be. The awesome people over at
[Sauce Labs][sauce-labs] may have just what you need. If you're doing Selenium
testing, they have infrastructure set up to help you spin up one of their
[many, many browsers][sauce-browsers]. They even have mobile browsers to use.
The best part? If your project is open source, their [Open Sauce][open-sauce]
plan is completely free.

Part of their setup is called [Sauce Connect][sauce-connect], which sets up a
tunnel from your server to their servers so they can access your webserver. We
want testing to be as easy as possible, so we have added first-class support
for Sauce Connect right in your .travis.yml config file. In order to enable
Sauce Connect, all you need to add to your .travis.yml file is this:

    addons:
      sauce_connect:
        username: your_username
        access_key: your_sauce_access_key

The `username` and `access_key` fields support encryption, so you don't have to
put them in your repository as plaintext. Read more about this in the
[addons docs][addons].

This is available on both Pro and Org VMs starting today. Go try it out!

[sauce-labs]: https://saucelabs.com
[sauce-browsers]: https://saucelabs.com/docs/browsers
[open-sauce]: https://saucelabs.com/signup/plan/OSS
[sauce-connect]: https://saucelabs.com/docs/connect
[addons]: http://about.travis-ci.org/docs/user/encryption-keys/
