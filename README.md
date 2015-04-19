Ansible Role of Owncloud
=========

Install owncloud.

Remarks
------------



Requirements
------------

* OS: CentOS 6/7

I've checked on CentOS 6.5 and 7.0.

Role Variables
--------------

* ``owncloud_db_add_on_mysql_enable``
  * If you want to create table for external storages, set this variable to ``true``.
  * If you set ``true``, following variables are needed
  * ``owncloud_db_host``: default value is localhost
  * ``owncloud_db_user``: default value is ``owncloud``
  * ``owncloud_db_pass``: default value is ``owncloud``
  * ``owncloud_db_table_name_to_be_created``:
  * ``owndloud_db_table``
    * ``name_to_be_created``: the default value is ``owncloud``
    * ``collation``: the default value is ``utf8_general_ci``
    * ``encoding``: the default value is ``utf8``

* ``owncloud_php_timezone``: timezone configuration in ``/etc/php.ini``
* ``owncloud_php_default_char``: timezone configuration in ``/etc/php.ini``.

Dependencies
------------

* ``magnus919.epel``: for installation of EPEL for CentOS systems
* ``hostclick.remi_repo``: for addition of Remi repository for CentOS systems


Example Playbook
----------------

    - hosts: owncloud
      sudo: yes
      roles:
        - owncloud
      vars:
        owncloud_db_host: "{{ hostvars['other-db-host']['ansible_eth0']['ipv4']['address'] }}"

License
-------

MIT

Author Information
------------------

Kenta Nishimura, data-science infrastructure engineers at a telecommunications company.
