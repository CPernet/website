---
title: I am having problems downloading
tags: [faq, download]
redirect_from:
  - /faq/i_am_having_problems_downloading_from_the_ftp_server/
---

# I am having problems downloading

{% include markup/warning %}
In the past we used an FTP server to distribute files, but as of April 2022 we switched to a new download server that can be found on <https://download.fieldtriptoolbox.org>. It supports [WebDAV](https://en.wikipedia.org/wiki/WebDAV), which means that you can download individual files using your web browser. You can also download a complete directory (with subdirectories) at once using a specialized WebDAV client such as [CyberDuck](http://cyberduck.io/) or [FileZilla](http://filezilla-project.org/). On Windows and macOS you can even mount the WebDAV server as a “network file system” and treat it as a network drive.

The information below therefore probably does not apply to you at the moment, but is kept for reference.
{% include markup/end %}

## I am having problems downloading from the FTP server

The FieldTrip source code and the example and tutorial datasets are released to the general public on our [FTP server](ftp://ftp.fieldtriptoolbox.org/pub/fieldtrip/). This server requires an anonymous login; if needed you should use the username "anonymous" and you can your email address (or anything that is formatted as an email address) as the password.

The FTP service runs on a shared server which occasionally has a performance bottleneck. If you cannot connect, please try again at a later time (i.e. one hour later, or the next day).

If downloading from the FTP server in the web browser continues to give problems, please try the following:

1. try it with another web browser, such as [Chrome](https://www.google.com/chrome/), [Firefox](http://getfirefox.org), Safari or Edge
2. try it with a specific [ftp client](https://www.google.com/search?q=ftp+client), such as [CyberDuck](https://cyberduck.io) or [FileZilla](https://filezilla-project.org)

If none of these resolves it, you can continue with the following suggestions.

### Enable support for FTP URLs in Chrome

Chrome has an option `#enable-ftp` that you can find by typing `chrome://flags/` in the address bar.  When enabled, the browser will handle navigations to URLs that start with `ftp://` by either showing a directory listing or downloading the resource over FTP. When disabled, the browser has no special handling for `ftp://` URLs and by default defers the handling of the URL to the underlying platform.

### Set the default application handler for FTP URLs in Windows

In Windows you navigate to "Windows System settings", then "Standard applications", and then "Standard applications per protocol". There you can select which application is to be used to handle FTP. If the list is empty, you should install an [ftp client](https://www.google.com/search?q=ftp+client) such as [CyberDuck](https://cyberduck.io) or [FileZilla](https://filezilla-project.org), or you should allow Chrome to deal with FTP URLs (see below).

### Set the default application handler for FTP URLs in macOS

On macOS you open "System Ppreferences" and then "Default Apps". Under the section "Internet" you can specify which applications should be used for Web, Email, News and FTP.

### Linux or macOS command-line client

If your difficulties are with the Linux or macOS command line ftp client, you can try to turn off "Extended Passive Mode" by typing `epsv`.

### CyberDuck

A strategy that was reported to work for CyberDuck is to add a bookmark ("plus" sign at the bottom left). Then it still needed a restart before it would actually connect. See the screenshot below.

{% include image src="/assets/img/faq/ftp/cyberduck.png" width="500" %}

## GitHub as alternative

The FieldTrip release versions are also available as zip-files from <https://github.com/fieldtrip/fieldtrip/tags>.

You can also use git to keep up to date with the stable release version or the latest development updates of the source code on the `release` or `master` branch. This allows you to revert to older versions, and to track and inspect all individual changes to the files.

Using the stable `release` or development `master` versions from GitHub requires that you have git client installed on your computer. When working on a Linux or macOS computer, git will probably be installed by default, so you can open a terminal and type

    git clone https://github.com/fieldtrip/fieldtrip.git fieldtrip
    cd fieldtrip
    git checkout release

To keep up to date with the latest release version, you would type

    cd fieldtrip
    git checkout release
    git pull upstream release
    
Although it is not required to just download the code, you could also make an account on GitHub and clone the FieldTrip repository there. That would allow you to contribute your suggestions and improvements back to the project as pull requests. See the [git tutorial](/development/git) for more details.

    
