Perlbrew
=========

This "perlbrew" role allow you to install perlbrew on Ubuntu / Debian / CentOS | RedHat.

[Perlbrew](http://perlbrew.pl) is a admin-free perl installation management
tool.

Requirements
------------

Ansible 1.6.x

Tested on
---------

1.9.2

Role Variables
--------------

* "perl_version" is used to specify the default perl version. Note: This cannot be `latest`, but need to be something like `perl-5.22.0`. The default will be changed to the latest stable.
* "perlbrew_user" is used to specify which user on the remote system that will get perlbrew.
* "switch_to_new_perl" is used to activate (`perlbrew switch`) the new perl_version right away, default is `true` (if `false` added lines in `.profile`/`.bashrc` will be commented)
* "perlbrew_as" name of the perlbrew namespace

Example config:

    ---
    perl_version: perl-5.22.0
    perlbrew_user: www
    switch_to_new_perl: true
    perlbrew_as: myperl

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - role: perlbrew 
          perlbrew_user: tobybro
          perl_version: perl-5.22.0
          perlbrew_as: myawesomeperl

License
-------

BSD

Author Information
------------------

Original author: Jan Henning Thorsen - jhthorsen@cpan.org - http://thorsen.pm
Slightly modified by: Toby Broyles
