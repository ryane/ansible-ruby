Role Name
=========

This role installs the specified ruby version from source. It will also install [Bundler](http://bundler.io/).

Requirements
------------

This role requires Ansible 1.7 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

The list of variables that must be set:

    # The ruby version to install
    ruby_version: 2.1.3

    # The SHA256 checksum of the Ruby source package
    ruby_source_checksum: 0818beb7b10ce9a058cd21d85cfe1dcd233e98b7342d32e9a5d4bebe98347f01

    # The url to download the source package.
    ruby_source_url: http://cache.ruby-lang.org/pub/ruby/2.1/ruby-{{ruby_version}}.tar.gz

The list of variables that can be set (but you shouldn't have to):

    # The location on the server where the Ruby source will be downloaded and compiled
    ruby_temp_directory: /usr/local/src

    # The list of apt packages that need to be installed to build ruby:
    ruby_apt_dependencies:
      - autoconf
      - build-essential
      - libreadline-dev
      - libssl-dev
      - libyaml-dev
      - zlib1g-dev
      - libsqlite3-dev
      - libxml2-dev
      - libxslt1-dev
      - curl

Dependencies
------------

None

Example Playbook
----------------

Install the specified Ruby version:

    - hosts: appservers
      roles:
         - role: ansible-ruby
           ruby_version: 2.1.3
           ruby_source_checksum: 0818beb7b10ce9a058cd21d85cfe1dcd233e98b7342d32e9a5d4bebe98347f01
           ruby_source_url: http://cache.ruby-lang.org/pub/ruby/2.1/ruby-{{ruby_version}}.tar.gz

License
-------

The MIT License (MIT)

Copyright (c) 2014 Ryan Eschinger

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Author Information
------------------

Ryan Eschinger | [Github](https://github.com/ryane) | [@ryanesc](https://twitter.com/ryanesc) | [http://ryaneschinger.com](http://ryaneschinger.com)
