Role Name
=========

Static Path Role. This role creates static path bindings for an EPG (created in the Tenant role).

Requirements
------------

An EPG for the static path binding has been created.

Role Variables
--------------

There are role variables set, but they are commented out. The only variable is `csv_role_path` which provides the full path for the read_csv module to get to the CSV file in the `files` directory.

Dependencies
------------

This particular role uses the read_csv module so the csv file under files must be populated with information such as Tenant, Application Profile, etc.

Example Playbook
----------------

License
-------

BSD

Author Information
------------------
