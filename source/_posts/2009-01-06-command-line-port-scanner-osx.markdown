---
layout: post
title: 'Command Line Port Scanner OSX'
date: 2009-01-06 09:34
comments: true
categories : [General, CLI, OSX]
---  

Who knew that OS X has a command line port scanner? I for one didn't. I've always just used the Network Utility version. Here's how to access it.

As the superuser run this:

{% codeblock %}
ln /Applications/Utilities/Network\ Utility.app/Contents/Resources/stroke /bin/stroke
chmod uo+x /bin/stroke
{% endcodeblock %}

Then as any user you can call it from the terminal as such:

{% codeblock %}
stroke address startPort endPort`
{% endcodeblock %}

So to check your local machine do:

{% codeblock %}
stroke 127.0.0.1 0 1024
{% endcodeblock %}

You should see output that looks similar to this:

{% codeblock %}
Port Scanning host: 127.0.0.1

         Open TCP Port:         80              http
         Open TCP Port:         631             ipp
{% endcodeblock %}

