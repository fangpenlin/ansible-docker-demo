ansible-docker-demo
===================

A simple ansible project for demonstrating how to build a docker image

Run the demo
============

To run this demo, you need to install ansible and [vagrant](http://www.vagrantup.com) with vbguest plugin. Then

```
vagrant up
```

Then, let's build the image, here you run

```
ansible-playbook \
  -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory \
  -u vagrant --private-key=~/.vagrant.d/insecure_private_key \
  playbooks/hellobaby.yml
```

It will prompt you which version and interation number to build like this

```
hellobaby_version [1.0.0]: 
hellobaby_iteration [1]: 
```

Just press enter twice to use the default value. Have a break, it should be done pretty soon.
