# week6_basic_ansible

this playbook will create and provision all web servers within the network with the weight tracker app 

# steps
### change ansible.cnf on folder /etc/ansible to allow connection without key exchanges

### change hosts file for different targets

### run ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username>
  
### you can add -vvv to have verbose:
ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> -vvv

### you can add few flags for debugging:  
run ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> --step

the last command will ask you to confirm each step

run ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> --start-at-task:"<name of the task>"
  
the last command will start the playbook on the requested task name

### you can mix and use the commands all together

# the weight tracker app:
 
# Node.js Weight Tracker

![Demo](docs/build-weight-tracker-app-demo.gif)

This sample application demonstrates the following technologies.

* [hapi](https://hapi.dev) - a wonderful Node.js application framework
* [PostgreSQL](https://www.postgresql.org/) - a popular relational database
* [Postgres](https://github.com/porsager/postgres) - a new PostgreSQL client for Node.js
* [Vue.js](https://vuejs.org/) - a popular front-end library
* [Bulma](https://bulma.io/) - a great CSS framework based on Flexbox
* [EJS](https://ejs.co/) - a great template library for server-side HTML templates

**Requirements:**

* [Node.js](https://nodejs.org/) 12.x or higher
* [PostgreSQL](https://www.postgresql.org/) (can be installed locally using Docker)
* [Free Okta developer account](https://developer.okta.com/) for account registration, login

## Install and Configuration

1. Clone or download source files
1. Run `npm install` to install dependencies
1. If you don't already have PostgreSQL, set up using Docker
1. Create a [free Okta developer account](https://developer.okta.com/) and add a web application for this app
1. Copy `.env.sample` to `.env` and change the `OKTA_*` values to your application
1. Initialize the PostgreSQL database by running `npm run initdb`
1. Run `npm run dev` to start Node.js

The associated blog post goes into more detail on how to set up PostgreSQL with Docker and how to configure your Okta account.

  
  
