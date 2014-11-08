CKAN Dev Environment
====================

The aim of this repository is to allow to setup a CKAN local development environment rapidly and also be able to reuse the ansible configuration scripts to provision a remote development environment or possibly a production instance.

Prerequisite
  * Vagrant 1.6.3+
  * Ansible 1.7+

To install the development environment run (this is only tested on OSX but should work on Linux).

  * ```git clone https://github.com/iilab/ckan-dev.git```
  * ```cd ckan-dev```
  * ```vagrant up``` (The provisioning will take a long time as it is building couch from source currently.)
    * Might have to download the ffuenf/debian-7.7.0-amd64 box like so:
```
vagrant box add ffuenf/debian-7.7.0-amd64 https://googledrive.com/host/0B83ZToJ3fGtDVC1DeVVzc3lkc0U/debian-7.7.0-amd64_virtualbox.box
```
  * (```vagrant provision```) Only necessary if you modify the playbook or need to provisioning an existing and running vagrant VM.

You should be able to access CKAN at ```http://localhost:8080``` 

## ToDO

  * Create custom docker ckan build.
  * Link custom docker ckan build to host docker volume.
  * Link host docker volume to vagrant shared folder.
  * Create ansible tags for executing maintenance commands (http://docs.ckan.org/en/latest/maintaining/installing/install-using-docker.html#running-maintenance-commands)
  * Create shell script for executing ansible tags (as in https://github.com/iilab/ltfhc-config/blob/master/run.sh)

This should allow to develop directly in a directory of the developer's computer and be able to execute basic maintenance tasks from outside the vagrant box.

