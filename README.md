# Google Chrome

![Puppet Google Chrome CI](https://github.com/GEANT/puppet-google-chrome/workflows/Puppet%20Google%20Chrome%20CI/badge.svg?branch=master)
[![Puppet Forge](https://img.shields.io/puppetforge/v/jamesnetherton/google_chrome.svg)](https://forge.puppet.com/jamesnetherton/google_chrome)
[![Puppet Forge](https://img.shields.io/puppetforge/f/jamesnetherton/google_chrome.svg?maxAge=600)](https://forge.puppet.com/jamesnetherton/google_chrome)
[![Puppet Forge](https://img.shields.io/puppetforge/dt/jamesnetherton/google_chrome.svg?maxAge=600)](https://forge.puppet.com/jamesnetherton/google_chrome)
[![Puppet Forge](https://img.shields.io/puppetforge/rc/jamesnetherton.svg?maxAge=600)](https://forge.puppet.com/jamesnetherton/google_chrome)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=600)](https://opensource.org/licenses/MIT)

## Table of Contents

1. [Overview](#overview)
2. [Usage](#usage)
3. [Notes](#notes)

## Overview

Puppet module to install the Google Chrome web browser module. Currently supports installation on:

* CentOS / Fedora
* Debian / Ubuntu
* openSUSE

## Usage

To install the stable version of Google Chrome, include or declare the google_chrome class.

```puppet
include google_chrome
```

```puppet
class { 'google_chrome':
}
```

To install unstable or beta versions, set the appropriate version attribute.

```puppet
class { 'google_chrome':
  version => 'unstable',
}
```

```puppet
class { 'google_chrome':
  version => 'beta',
}
```

To modify the full set of default parameters.

```puppet
class { 'google_chrome':
  ensure                 => 'installed',
  version                => 'unstable',
  package_name           => 'google-chrome',
  repo_gpg_key           => 'https://dl.google.com/linux/linux_signing_key.pub',
  repo_gpg_key_id        => '4CCA1EAF950CEE4AB83976DCA040830F7FAC5991',
  repo_gpg_key_options   => 'http-proxy="http://proxyuser:proxypass@example.org:3128"',
  repo_name              => 'google-chrome',
  defaults_file          => '/etc/default/google-chrome',
  defaults_proxy_pac_url => 'http://foo/bar/proxy.pac',
  repo_base_url          => 'https://dl.google.com/linux/chrome/rpm/stable/x86_64'
}
```

## Notes

Forked from [jamesnetherton/google_chrome](https://forge.puppetlabs.com/modules/jamesnetherton/google_chrome/readme)
