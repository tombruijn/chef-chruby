# chruby cookbook

Installs the Chruby utility for changing between Ruby versions.
Chruby is a vastly simplified rbenv - it's about 90 lines of code, and
very easy to understand.

# Requirements

- Depends on the `ark` cookbook.
- Tested on:
  - CentOS 6.3 and 6.4
  - CentOS 5.8
  - Ubuntu 12.04
  - Ubuntu 10.04

# Usage

Include the `chruby` recipe in your run list. This will make the
chruby tool available to every shell, and make the embedded Ruby from
the Omnibus install available for use.

To install Ruby versions it's recommended that you use a different cookbook.
There are a couple variants; for different Ruby installers and installation
approaches. They all work with this cookbook without any special configuration,
just follow the instructions in their readme's.

The list currently is (and is always open to new additions):

- [ruby-install](https://github.com/tombruijn/chef-ruby-install)
  - Uses Postmodern's [ruby-install](https://github.com/postmodern/ruby-install)  
    to install Ruby versions.  
    Installation of ruby-install and rubies through a recipe. More configuration
    options through providers.

- [ruby_install](https://github.com/rosstimson/chef-ruby_install)
  - Uses Postmodern's [ruby-install](https://github.com/postmodern/ruby-install)
    to install Ruby versions.  
    Installation of ruby-install through a recipe and rubies through providers.

- [ruby_build](https://github.com/fnichol/chef-ruby_build)
  - Uses Sam Stephenson's [ruby-build](https://github.com/sstephenson/ruby-build)
    to install Ruby versions.  
    Installation of ruby-build through a recipe and rubies through providers.

# Attributes

- `node['chruby']['version']` - the version of Chruby to install.  Default is 0.3.4.
- TODO: `node['chruby']['gpg_check']` - run the GPG check to verify the release was not tampered with.
- `node['chruby']['use_rvm_rubies']` - make Rubies installed using RVM available to chruby.
- `node['chruby']['use_rbenv_rubies']` - make Rubies installed using Rbenv available to chruby.
- `node['chruby']['auto_switch']` - enable automatic switching between Ruby versions per https://github.com/postmodern/chruby#auto-switching
- `node['chruby']['default']` - specify the default Ruby version for every shell.
- `node['chruby']['user_rubies']` - an array of directories containing custom rubies

# Recipes

## Default

Installs the chruby utility, and makes it available to every shell.
If Chef was installed with the Omnibus installer, make embedded Ruby
available as an option for usage.

# Author and License

- Author: Stephen Nelson-Smith (LordCope) - Atalanta Systems Ltd (<cookbooks@atalanta-systems.com>)

Copyright 2013, Atalanta Systems Ltd

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
