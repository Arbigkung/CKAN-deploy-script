How to deploy CKAN from Ansible and Jenkins

1. Install Ansible 
docs.ansible.com/ansible/intro_installation.html#latest-releases-via-apt-ubuntu

2. Setup Ansible inventory file for connect to deployed host and run command 
ansible-playbook -i aws -vvvvv init.yml

3. Deploy Jenkins
- Via docker https://hub.docker.com/_/jenkins/
- add ssh config following to example and test to connect with server
- add ckan command line to run docker ckan inside docker container
  - docker run -d --name db ckan/postgresql; docker run -d --name solr ckan/solr; docker run -d -p 80:80 --link db:db --link solr:solr ckan/ckan

4. Fix CKAN container according to issue
- github.com/ckan/ckan/issues/3130 
