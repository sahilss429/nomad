# Nomad and consul work under progress.
1. clone the repository.
2. Run vagrant up in the directory
3. Run ansible - before that make sure you have docker installed:
 - Setup nomad and consul servers:
docker run --rm -it -v `pwd`:/ansible/playbooks -v ~/.ssh/id_rsa:/root/.ssh/id_rsa -v ~/.ssh/id_rsa.pub:/root/.ssh/id_rsa.pub philm/ansible_playbook -i inventory/clients -vv configure_nomad-server.yml
 - Setup nomad and consul clients:
docker run --rm -it -v `pwd`:/ansible/playbooks -v ~/.ssh/id_rsa:/root/.ssh/id_rsa -v ~/.ssh/id_rsa.pub:/root/.ssh/id_rsa.pub philm/ansible_playbook -i inventory/clients -vv configure_nomad-client.yml
