umatrix2ublock
==============

Migrate rulesets from uMatrix_ to uBlock-Origin_.

.. warning::

   Websites are very likely to break with this setup, so have uBlock-Origin disabled
   in private windows such that you have a fallback option.

An effort is made to retain similar functionality and blocking as before.

Usage
-----

1. Opt-in under uBlock-Origin_ settings: "I am an advanced_ user". Then *block*
   3rd-party scripts and *noop* 3rd-party frames globally.

   .. image:: https://user-images.githubusercontent.com/9155111/75360210-c96e5f00-58b5-11ea-9e76-73012e3d30d5.png

2. Either enable "Custom" Firefox Enhanced Tracking protection to block all
   third-party cookies, or use Cookie-AutoDelete_.

3. Export your existing uMatrix_ and uBlock-Origin_ rules into text files.
   Execute it something similar to::

     cd examples/
     python ../umatrix2ublock.py my-umatrix-rules.txt my-ublock-dynamic-rules_2020-02-26_14.07.25.txt

   to obtain a merged ruleset ``my-ublock-dynamic-rules.txt`` compatible with
   uBlock-Origin_.

4. Import the merged ruleset into uBlock-Origin_.

Background
----------

In my browser, I originally had uBlock-Origin_ (with its default settings) and
uMatrix_.

I started using uMatrix_ to block all third-party requests by default (except
css and images), and whitelisting a few requests to make the website is
functional.

.. image:: https://user-images.githubusercontent.com/585534/33213085-ff74afd8-d0f3-11e7-8232-4c204925d274.png

I realized later that most of the time, I was just whitelisting scripts and
XHRs. Which meant in principle, I can rely on custom settings as mentioned
above. I simply needed to migrate my uMatrix_ rules that I had aggregated over
several months to serve the same purpose.


.. _advanced: https://github.com/gorhill/uBlock-Origin/wiki/Advanced-user-features
.. _uMatrix: https://github.com/gorhill/uMatrix
.. _uBlock-Origin: https://github.com/gorhill/uBlock
.. _Cookie-AutoDelete: https://github.com/Cookie-AutoDelete/Cookie-AutoDelete
