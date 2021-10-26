## configuration management example with ansible

this ansible playbook will provision servers within the network with the weight tracker app 
and also will use SSO with the okta service

# the steps
first step:

1. create new app in the okta dev platform : [Free Okta developer account](https://developer.okta.com/) for account registration, login
2. copy all the info needed for the .env file (see examle env file below)
3. fork https://github.com/entebox/bootcamp-app.git to your github page 
   and use it on the playbook file as the variable name - repo(the one you forked): < add repo containing the app files including .env file >

in order to have first contact between the ansible server to the clients we can use two options:
1. (which is less secured) change ansible.cnf on folder /etc/ansible to allow connection without key exchanges -
on the file, search for the line: `host_key_checking = False` .

2. (which is better) Create ssh key and copy it to the remote machines:
https://myadventuresincoding.wordpress.com/2011/12/22/linux-how-to-ssh-between-two-linux-computers-without-needing-a-password/

second step:
1. edit the hosts file (inventory file) related to your environment
2. edit the variables inside the playbook file that suits to your environment:

### example for .env file:

```
# Postgres configuration
PGHOST=< pg host >
PGUSERNAME=< pg user name >
PGDATABASE=< pg database >
PGPASSWORD=< pg password >
PGPORT=5432
#Node Weight Tracker
HOST_URL=< host url >
COOKIE_ENCRYPT_PWD=< cookie password >
NODE_ENV=development
# Okta configuration
OKTA_ORG_URL=< okta url >
OKTA_CLIENT_ID=< okta client id >
OKTA_CLIENT_SECRET=< okta client secret >
```

run `ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username>`
  
### you can add few flags for debugging:
this command will show debugging output 
`ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> -vvv`

this command will ask you to confirm each step
`ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> --step`

this command will start the playbook on the requested task name
`ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> --start-at-task:"<name of the task>"`

## about the application:
# Node.js Weight Tracker

![Demo](docs/build-weight-tracker-app-demo.gif)

This sample application demonstrates the following technologies.

* [hapi](https://hapi.dev) - a wonderful Node.js application framework
* [PostgreSQL](https://www.postgresql.org/) - a popular relational database
* [Postgres](https://github.com/porsager/postgres) - a new PostgreSQL client for Node.js
* [Vue.js](https://vuejs.org/) - a popular front-end library
* [Bulma](https://bulma.io/) - a great CSS framework based on Flexbox
* [EJS](https://ejs.co/) - a great template library for server-side HTML templates

  
  
