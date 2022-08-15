# Coding challenge II: Save our deploy train

## Tools needed to achieve this challenge:

- **Ansible**

  Once Ansible got installed in our machine. we should firstly configure the `/etc/ansible/hosts and` and `/etc/ansible/ansible.cfg` so the ping can be succeded .

- **Docker & docker-compose**

  Compose is a tool for defining and running multi-container Docker application. Compose use yml file to configure application's services.

## The How!

  1- We simply define our containers in a file called dokcer-compose.yml, we use port `80:80` for nginx container and `9000` for php container. we mount the directory `~/forchallenge/conf.d/` on the host as `/etc/nginx/conf.d` inside the container. And we do the same for `/var/www/html` where the static application is hosted.
  
  2- We create a file called ansible_playbook_for_docker_compose.yml, where we define the host and tasks for the playbook. We configure the task so ansible can run docker-compose.yml automatically. 

  3- Here we cannot use docker-compose module since ansible in not yet support the variable `link`. 


