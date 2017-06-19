The chef-repo
===============
All installations require a central workspace known as the chef-repo. This is a place where primitive objects--cookbooks, roles, environments, data bags, and chef-repo configuration files--are stored and managed.

The chef-repo should be kept under version control, such as [git](http://git-scm.org), and then managed as if it were source code.

Knife Configuration
-------------------
Knife is the [command line interface](https://docs.chef.io/knife.html) for Chef. The chef-repo contains a .chef directory (which is a hidden directory by default) in which the Knife configuration file (knife.rb) is located. This file contains configuration settings for the chef-repo.

The knife.rb file is automatically created by the starter kit. This file can be customized to support configuration settings used by [cloud provider options](https://docs.chef.io/plugin_knife.html) and custom [knife plugins](https://docs.chef.io/plugin_knife_custom.html).

Also located inside the .chef directory are .pem files, which contain private keys used to authenticate requests made to the Chef server. The USERNAME.pem file contains a private key unique to the user (and should never be shared with anyone). The ORGANIZATION-validator.pem file contains a private key that is global to the entire organization (and is used by all nodes and workstations that send requests to the Chef server).

More information about knife.rb configuration options can be found in [the documentation for knife](https://docs.chef.io/config_rb_knife.html).

Cookbooks
---------
A cookbook is the fundamental unit of configuration and policy distribution. A sample cookbook can be found in `cookbooks/starter`. After making changes to any cookbook, you must upload it to the Chef server using knife:

    $ knife upload cookbooks/starter

For more information about cookbooks, see the example files in the `starter` cookbook.

Roles
-----
Roles provide logical grouping of cookbooks and other roles. A sample role can be found at `roles/starter.rb`.

Getting Started
-------------------------
Now that you have the chef-repo ready to go, check out [Learn Chef](https://learn.chef.io/) to proceed with your workstation setup. If you have any questions about Chef you can always ask [our support team](https://www.chef.io/support/) for a helping hand.

CrashCourse
-----------


Comands
- berks install :: Manejador de dependencias
- berks upload :: Realiza cambios a tu chef server
- knife client list :: Show keys!
- knife cookbook list :: Show cookbook list from server
- knife boostrap FQDN -x USER -P PWD —sudo -N NODENAME :: Inicia un nodo
- knife node run_list add NODENAME "recipe[apache]" :: Agrega receta a un nodo
- knife node show NODENAME -a cloud :: Info de tus nodos locales
- knife node show NODENAME -a cloud.public_ipv4 :: Identifica unicamente el atributo public_ipv4
- knife search "*:*" -a cloud 
- knife search "*:*" -a cloud.public_ipv4



Resources
---------
- http://bit.ly/1Xoai9R
- http://bit.ly/1pQo0qd
- http://bit.ly/1pQnwQZ
- https://learn.chef.io/modules/beyond-the-basics/
- https://docs.chef.io/berkshelf.html
- https://api.chef.io:443/organizations/ORGANIZATIONNAME
