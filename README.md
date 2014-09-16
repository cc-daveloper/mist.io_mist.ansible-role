mist.ansible-role
==================

This role will take care of installing the mist.io service.

Summary
-------

This role will take care to clone the mist.io service from the https://github.com/mistio/mist.io repository,
install the necessary packages and init the mist.io service in a virtualenv.

After finishing you can visit http://your-server:8000 to have access to the mist.io service

Requirements
------------

You need to have a non root user added to the sudoers.

Role Variables
--------------

The variables that can be passed:

    #If jsbuild and cssbuild are True, then precompiled js and css templates will be used.
    #This results in faster load times, however you can't debug js and css.
    #Use False in case of development.
    jsbuild                    : True
    cssbuild                   : True

    #sslverify will verufy that a https installation has a valid certificate.
    sslverify                  : False

You can find and change this variables in the defaults/main.yml file

Example Playbook
----------------

Simple example:

    ---

    - name: Example playbook for mist.io service
      hosts: mistserver
      vars_files:
        - "defaults/main.yml"

      tasks:
        - include: "tasks/main.yml"

