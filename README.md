# centos7aptest
The Dockerfile for centos7aptest

## File requirements
Inventory file(mine is named prod)

site.yml file

## Setup
Need an inventory file with the following:
```
[docker]
127.0.0.1 ansible_connection=local
```

and a site.yml file with the following as an example:
```
- hosts: docker
  roles:
    - docker-ce
 ```
 
 Then run the following command to run the role in a centos7 container:
 ```
 docker run -it --rm -v $(pwd):/ansible centos7aptest:v1 ansible-playbook -i /ansible/prod /ansible/site.yml
 ```
 
 Just watch the output and the container will be removed after the job is finished.
