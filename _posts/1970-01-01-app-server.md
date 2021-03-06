---
layout: post
title: Know your App Server!
order: 140
---

Running a Rails app starts a WEBrick server by default. This is good enough for the development environment, but not for production. WEBrick runs code in a single thread, and can not handle requests concurrently.

It is very important to understand the different operating models of threaded and event-loop based servers, to select the most reliable and efficient server for your app.

Another aspect is how static files are handled. Do not waste CPU time by giving this task to a Ruby app. Give this work to reverse proxy servers like Nginx. They can also handle other things, like proxying (e.g. 3000 port to 80 port), multi-domain setup, limiting requests per second to prevent DDoS, "slow client" attack, etc.

TODO: Make a brief description of different models  

* [Rubyraptor: Description of different operation models in Rack servers](http://www.rubyraptor.org/how-we-made-raptor-up-to-4x-faster-than-unicorn-and-up-to-2x-faster-than-puma-torquebox/)
* [A comparison of Rack web servers for Ruby web applications](https://www.digitalocean.com/community/tutorials/a-comparison-of-rack-web-servers-for-ruby-web-applications)
* [Puma](https://github.com/puma/puma)
* [Unicorn](https://github.com/defunkt/unicorn)
* [Passenger](https://www.phusionpassenger.com/)
* [Nginx](http://nginx.org/)
