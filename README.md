# NextBook

A privacy-respecting alternative to Google's [Chromebook](https://en.wikipedia.org/wiki/Chromebook) and ChromeOS.


## Why?

For many computer users the Chromebook is a great solution.  They are inexpensive, require almost no maintenance and are interchangeable in the sense that you can log-on to any Chromebook and almost immediately pick-up where you left off on the last one.  

The downside of all this convenience is that everything you relies on Google, and there are numerous, well-documented reasons you might want to avoid this.

It's hard for me to recommend Chromebooks to people because of these privacy concerns, but at the same time I'm not aware of any alternative that provides the essential safety and low cost of ownership.  This tension is the motivation behind NextBook.


## Overview

NextBook provides the Chromebook experience without requiring the user to trust proprietary software or services.  In place of ChromeOS is a Debian-based Linux distribution that can be installed on almost any hardware to create a Chromebook-like device.  In place of Google's services and applications, NextBook uses [NextCloud](), and a custom set of NextCloud applications to provide NextBook-specific features such as system updates, access to local storage, battery level, etc.

NextBook ships configured for a default NextCloud server provided by the project.  This allows the user to get up-and-running with the same amount of effort as a Chromebook.  For greater privacy and control, NextBook can deploy a private NextCloud server to one of several hosting services automatically.  If you already have a NextCloud server, NextBook can connect to that as well<sup>[1](#fn1)</sup>


## Details

NextBook is being built using the following projects:

* [Debian](https://www.debian.org/)
* [RESTMetal](https://codeberg.org/jjg/restmetal)
* [Firefox](https://www.mozilla.org/en-US/firefox/new/)
* [NextCloud](https://nextcloud.com/)
* Custom NextCloud web applications (TBD)

1. Debian boots the hardware and provides a minimal runtime environment for Firefox
2. RESTMetal exposes local hardware resources to web applications (network configuration, battery level, system utilization, etc.)
3. Firefox runs full-screen as the sole X11 application and is used for all user interface elements
4. Firefox connects to the selected NextCloud server for authentication, or to a local Web app for setup if not configured

Once authenticated, the user is presented with a "launcher" as the default NextCloud application.  The exact details of this are not yet determined but any existing NextCloud functionality that meets the criteria will be considered first.  In addition to existing NextCloud applications, several new applications will need to be developed to provide a user interface for the NextBook's local environment.  These include network configuration, battery level monitoring (if applicable), resetting the NextBook (akin to ChromeOS's "powerwash") and other tools as needed.



<a name="fn1">1</a>: For full NextBook functionality, NextBook applications will need to be installed on your NextCloud instance.
