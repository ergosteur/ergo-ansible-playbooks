## WordPress+Nginx+PHP-FPM+MariaDB Deployment

- Requires Ansible 1.2 or newer
- Expects Debian 8.x host/s

Debian version reflects differences in Debian tools and packagenames:  
1. yum -> apt  
2. firewalld and selinux config removed for now  
3. php-fpm -> php5-fpm  
4. config file locations for php5-fpm, nginx  
5. socket location for php5-fpm  
6. add php5-ldap and php5-gd

Playbook needs to be updated to add nginx official stable repo to get nginx 1.10

These playbooks deploy a simple all-in-one configuration of the popular
WordPress blogging platform and CMS, frontend by the Nginx web server and the
PHP-FPM process manager. To use, copy the `hosts.example` file to `hosts` and 
edit the `hosts` inventory file to include the names or URLs of the servers
you want to deploy.

Then run the playbook, like this:

	ansible-playbook -i hosts site.yml

The playbooks will configure MariaDB, WordPress, Nginx, and PHP-FPM. When the run
is complete, you can hit access server to begin the WordPress configuration.

### Ideas for Improvement

Here are some ideas for ways that these playbooks could be extended:

- Parameterize the WordPress deployment to handle multi-site configurations.
- Separate the components (PHP-FPM, MySQL, Nginx) onto separate hosts and 
handle the configuration appropriately.
- Handle WordPress upgrades automatically.

We would love to see contributions and improvements, so please fork this
repository on GitHub and send us your changes via pull requests.

