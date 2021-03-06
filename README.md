

Support
=======

Issues have been disabled for this repository.  
Any issues with this cookbook should be raised here:

[https://github.com/rcbops/chef-cookbooks/issues](https://github.com/rcbops/chef-cookbooks/issues)

Please title the issue as follows:

[mysql-openstack]: \<short description of problem\>

In the issue description, please include a longer description of the issue, along with any relevant log/command/error output.  
If logfiles are extremely long, please place the relevant portion into the issue description, and link to a gist containing the entire logfile
Description
===========

The Openstack recipes depend on osops-utils helper methods for defining access endpoints. This wrapper cookbook configures the required scaffolding for the mysql cookbook.

Requirements
============

Chef 0.10.0 or higher required (for Chef environment use).

Platforms
--------

* CentOS >= 6.3
* Ubuntu >= 12.04

Cookbooks
---------

The following cookbooks are dependencies:

* [keepalived](https://github.com/rcbops-cookbooks/keepalived)
* [mysql](https://github.com/rcbops-cookbooks/mysql)
* [openssl](https://github.com/opscode-cookbooks/openssl)
* [osops-utils](https://github.com/rcbops-cookbooks/osops-utils)

Resources/Providers
===================

None

Recipes
=======

default
----
- Includes recipe `mysql::server`
- Includes recipe `keepalived` if `mysql-db` VIP exists

Attributes
==========

* `mysql['services']['db']['scheme']` - Communication scheme
* `mysql['services']['db']['port']` - Port on which mysqld listens
* `mysql['services']['db']['network']` - `osops_networks` network name which service operates on

Templates
=========

None

License and Author
==================

Author:: Justin Shepherd (<justin.shepherd@rackspace.com>)  
Author:: Jason Cannavale (<jason.cannavale@rackspace.com>)  
Author:: Ron Pedde (<ron.pedde@rackspace.com>)  
Author:: Joseph Breu (<joseph.breu@rackspace.com>)  
Author:: William Kelly (<william.kelly@rackspace.com>)  
Author:: Darren Birkett (<darren.birkett@rackspace.co.uk>)  
Author:: Evan Callicoat (<evan.callicoat@rackspace.com>)  
Author:: Matt Thompson (<matt.thompson@rackspace.co.uk>)  
Author:: Andy McCrae (<andrew.mccrae@rackspace.co.uk)  

Copyright 2012, Rackspace US, Inc.  

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
