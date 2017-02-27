# Jenkins Slave Setup

[![Build Status](https://travis-ci.org/ChristopherDavenport/ansible-role-jenkins-slave.svg?branch=master)](https://travis-ci.org/ChristopherDavenport/ansible-role-jenkins-slave)

## Requirements

An ssh public key locally to transfer and authorize access for.

## Role Variables

`jenkins_slave_username` is the the user to user as the jenkins slave account.

`jenkins_slave_base` is the base directory for the jenkins slave account.

`jenkins_slave_mount` is the folder for shared folder mounting with jenkins,
if that is desired, such as in Higher Education.

`jenkins_slave_authorize_key` is the public key to authorize access to the
jenkins slave user. This will allow jenkins to access and control the slave
machine.

```yaml
jenkins_slave_username: jenkins
jenkins_slave_base: /home/{{ jenkins_slave_username }}
jenkins_slave_mount: "{{jenkins_slave_base}}/mount"

# Local Public Key File
# jenkins_slave_authorize_key:
```

## Dependencies

  - None

## Example Playbook

```yaml
- hosts: appserver
  vars:
    jenkins_slave_authorize_key: /home/fakeuser/jenkinsslave_rsa.pub
  roles:
    - ChristopherDavenport.jenkins-slave
```

## License

MIT

## Author Information

This role was created in 2016 by Christopher Davenport.
