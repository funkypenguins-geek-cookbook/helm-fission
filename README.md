
[cookbookurl]: https://geek-cookbook.funkypenguin.co.nz
[discourseurl]: https://discourse.geek-kitchen.funkypenguin.co.nz
[discordurl]: http://chat.funkypenguin.co.nz
[patreonurl]: https://patreon.com/funkypenguin
[blogurl]: https://www.funkypenguin.co.nz
[twitchurl]: https://www.twitch.tv/funkypenguinz
[twitterurl]: https://twitter.com/funkypenguin
[dockerurl]: https://geek-cookbook.funkypenguin.co.nz/ha-docker-swarm/design
[k8surl]: https://geek-cookbook.funkypenguin.co.nz/kubernetes/start
[![geek-cookbook](https://raw.githubusercontent.com/geek-cookbook/autopenguin/master/images/readme_header.png)][cookbookurl]
[![Discord](https://img.shields.io/discord/396055506072109067?color=black&label=Hot%20Sweaty%20Geeks&logo=discord&logoColor=white&style=for-the-badge)][discordurl]
[![Forums](https://img.shields.io/discourse/topics?color=black&label=Forums&logo=discourse&logoColor=white&server=https%3A%2F%2Fdiscourse.geek-kitchen.funkypenguin.co.nz&style=for-the-badge)][discourseurl]
[![Cookbook](https://img.shields.io/badge/Recipes-44-black?style=for-the-badge&color=black)][cookbookurl]
[![Twitch Status](https://img.shields.io/twitch/status/funkypenguinnz?style=for-the-badge&label=LiveGeeking&logoColor=white&logo=twitch)][twitchurl]

:wave: Welcome, traveller!
> The [Geek Cookbook][cookbookurl] is a collection of geek-friendly "recipes" to run popular applications on [Docker Swarm][dockerurl] or [Kubernetes][k8surl], in a progressive, easy-to-follow format.  ***Come and [join us][discordurl], fellow geeks!*** :neckbeard:

 
# Contents

1. [What is this?](#what-is-this)
2. [How to use it?](#how-to-use-it)
3. [Why it exists?](#why-it-exists)
4. [Upstream README](#upstream-readme)

 
# How to use it?

Use helm to add the repo:

```
helm repo add geek-cookbook https://geek-cookbook.github.io/charts/
```

Then simply install using helm, for example

```
kubectl create namespace fission
helm upgrade --install --namespace fission geek-cookbook/fission
```




# What is this?

This is a fork of fission/fission, so that I can self-host helmv3-compatible charts

# How to use it?

Edit another repo on the funkypenguins-geek-cookbook organization, in the `.penguin` folder

# Why it exists?

Because geeks like automating things (no, we are not just lazy :slightly_smiling_face:)

# Upstream README

# Fission: Serverless Functions for Kubernetes

[![Build Status](https://travis-ci.org/fission/fission.svg?branch=master)](https://travis-ci.org/fission/fission)
[![Go Report Card](https://goreportcard.com/badge/github.com/fission/fission)](https://goreportcard.com/report/github.com/fission/fission)

[fission.io](http://fission.io) | [@fissionio](http://twitter.com/fissionio) | [Slack](https://join.slack.com/t/fissionio/shared_invite/enQtOTI3NjgyMjE5NzE3LTllODJiODBmYTBiYWUwMWQxZWRhNDhiZDMyN2EyNjAzMTFiYjE2Nzc1NzE0MTU4ZTg2MzVjMDQ1NWY3MGJhZmE)

&lt;img src=&#34;https://docs.fission.io/images/logo.png&#34; width=&#34;300&#34;&gt;

Fission is a fast serverless framework for Kubernetes with a focus on
developer productivity and high performance.

Fission operates on _just the code_: Docker and Kubernetes are
abstracted away under normal operation, though you can use both to
extend Fission if you want to.

Fission is extensible to any language; the core is written in Go, and
language-specific parts are isolated in something called
_environments_ (more below).  Fission currently supports NodeJS, Python, Ruby, Go, 
PHP, Bash, and any Linux executable, with more languages coming soon.

# Performance: 100msec cold start

Fission maintains a pool of &#34;warm&#34; containers that each contain a
small dynamic loader.  When a function is first called,
i.e. &#34;cold-started&#34;, a running container is chosen and the function is
loaded.  This pool is what makes Fission fast: cold-start latencies
are typically about 100msec.

# Kubernetes is the right place for Serverless

We&#39;re built on Kubernetes because we think any non-trivial app will
use a combination of serverless functions and more conventional
microservices, and Kubernetes is a great framework to bring these
together seamlessly.

Building on Kubernetes also means that anything you do for operations
on your Kubernetes cluster &amp;mdash; such as monitoring or log
aggregation &amp;mdash; also helps with ops on your Fission deployment.

# Getting started and documentation

## Fission Concepts

Visit [concepts](https://docs.fission.io/docs/concepts/) for more details.

## Documentations

You can learn more about Fission and get started from [Fission Docs](https://docs.fission.io/docs).
* See the [installation guide](https://docs.fission.io/docs/installation/) for installing and running Fission.
* See the [troubleshooting guide](https://docs.fission.io/docs/trouble-shooting/) for debugging your functions and Fission installation.

## Usage

```bash
  # Add the stock NodeJS env to your Fission deployment
  $ fission env create --name nodejs --image fission/node-env

  # A javascript one-liner that prints &#34;hello world&#34;
  $ curl https://raw.githubusercontent.com/fission/fission/master/examples/nodejs/hello.js &gt; hello.js

  # Upload your function code to fission
  $ fission function create --name hello --env nodejs --code hello.js

  # Map GET /hello to your new function
  $ fission route create --method GET --url /hello --function hello

  # Run the function.  This takes about 100msec the first time.
  $ fission function test --name hello
  Hello, world!
```

# Contributing

## Building Fission
See the [compilation guide](https://docs.fission.io/docs/contributing/).

## Contact
Fission is a project by [many contributors](https://github.com/fission/fission/graphs/contributors).
Reach us on [slack](https://join.slack.com/t/fissionio/shared_invite/enQtOTI3NjgyMjE5NzE3LTllODJiODBmYTBiYWUwMWQxZWRhNDhiZDMyN2EyNjAzMTFiYjE2Nzc1NzE0MTU4ZTg2MzVjMDQ1NWY3MGJhZmE) or [twitter](https://twitter.com/fissionio).

## Community Meeting 

A regular community meeting takes place every other Thursday at 09:00 AM PT (Pacific Time). [Convert to your local timezone](http://www.thetimezoneconverter.com/?t=09:00&amp;tz=PT%20%28Pacific%20Time%29).

Meeting Link: https://zoom.us/j/413921817 

The meeting agenda for next meeting and notes from past meetnigs are maintained in [this document](https://docs.google.com/document/d/1E-xw4KJgka4sUpETHxr9BJBYntzrtxlAN_CE3Wt8kws). You are welcome to join to discuss direction of project, design and implementation reviews and general questions about project etc.

# Official Releases

Official releases of Fission can be found on [the releases page](https://github.com/fission/fission/releases). 
Please note that it is strongly recommended that you use official releases of Fission, as unreleased versions from 
the master branch are subject to changes and incompatibilities that will not be supported in the official releases. 
Builds from the master branch can have functionality changed and even removed at any time without compatibility support 
and without prior notice.

# Sponsors
The following companies, organizations, and individuals support Fission&#39;s ongoing maintenance and development.
Become a sponsor to get your logo on our README on Github with a link to your site.

&lt;p&gt;
    &lt;a href=&#34;https://infracloud.io/&#34;&gt;&lt;img src=&#34;https://fission.io/sponsors/infracloud.png&#34; alt=&#34;InfraCloud&#34; height=&#34;70&#34;&gt;&lt;/a&gt;
    &lt;a href=&#34;https://srcmesh.com/&#34;&gt;&lt;img src=&#34;https://fission.io/sponsors/srcmesh.png&#34; alt=&#34;Srcmesh&#34; height=&#34;70&#34;&gt;&lt;/a&gt;
&lt;/p&gt;

# Licensing

Fission is under the Apache 2.0 license.


