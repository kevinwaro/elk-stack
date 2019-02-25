# elk-stack

## Description

A set of ansible playbooks ran by Vagrant to setup two debian boxes: one running an ELK stack (Elasticsearch, Logstash, Kibana)
and one running a filebeat agent forwarding its logs to the ELK stack.

## Usage:

First clone the git repo:

    git clone https://github.com/kevinwaro/elk-stack.git && cd elk-stack

Then let Vagrant play the music:

    vagrant up

### Kibana Dashboard:

Once Vagrant has been ran, you can open your browser at the address http://192.168.200.10 to access to the kibana dashboard.

### Access to the boxes:

You can log into the boxes by running the following commands:

    vagrant ssh elasticsearch

or:

    vagrant ssh client

### Filebeat modules:

By default, on the filebeat agent, the follwing modules will already been enabled:

* apache2
* system
* nginx

## Credits:

* author: kevinwaro
* contact: kevinwaro@yahoo.fr

## Licence

This project is licensed under the GNU GPLv3 License - see the [License.md](License.md) file for details
