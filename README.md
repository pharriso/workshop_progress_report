Report progress on Ansible Workshops
=========

Sets up a cron job that runs every 5 minutes to work out how far students have got in their exercises. Report is available via the webserver. 

Note some flaws:

* relies on students creating playbooks with correct names
* only works for rhel workshop at the moment
* relies on you having deployed rocketchat server first

Requirements
------------

* A pre-deployed Ansible workshop node that has been convered to a rocketchat server.

Required Variables
------------

Edit the following variables in extra_vars.

| Name                      | Default value         |                                                                                  |
|---------------------------|-----------------------|----------------------------------------------------------------------------------|
| lab_domain                |                       | **REQUIRED** Domain for lab environment e.g. abcd.example.opentlc.com            |
| students                  |                       | **REQUIRED** Number of students                                                  |
| lab_password              |                       | **REQUIRED** Lab password                                                        |

Running the playbook
------------

Run the playbook as follows.


```bash
ansible-playbook setup_report_server.yml -u student1 -e @extra_vars
```
