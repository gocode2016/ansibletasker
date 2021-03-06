# Ansible Tasker

<p><a href="https://github.com/ansible">Ansible</a> is a radically simple IT automation system. It handles configuration-management, application deployment, cloud provisioning, ad-hoc task-execution, and multinode orchestration - including trivializing things like zero downtime rolling updates with load balancers.</p>
<p>And this is extremely simple web-admin panel for it designed for launching playbooks from browser. As example it configured for setup BOSH/Cloud Foundry/Redis and dummy playbooks. With small enhancements you can change that according to your needs but there are no reasons to do that because of a lot different free products for Ansible. Feel free to post suggestions/bugs.</p>
<p>Project page <a href="https://github.com/ipeacocks/ansibletasker">on Github</a></p>

## Demo

<p align="center">
  <img src="screenshots/ansibletasker.gif" />
</p>

## Requirements

This panel is written on:

* Bootstrap 3
* Python 3
* Flask Framework
* SQLAlchemy
* WTForms
* SQLite

## Installation

Clone code:
```
# git clone git@github.com:ipeacocks/ansibletasker.git
```
Simply create virtualenv:
```
# cd ansibletasker
# virtualenv --no-site-packages env
```
Make sure that `virtualenv` created env with `python3`.
Ansible needs `id_rsa` private key for authorization to remote host, so copy it to `ansible` dir:
```
# cp ~/.ssh/id_rsa ansible
```
Activate virtual env:
```
# source env/bin/activate
```
That's almost it. Use `requirments.txt` to setup all python dependencies:
```
# pip install -r project/requirements.txt
```
Create sqlite db:
```
# python project/db_create.py
```
And finally launch:
```
# python project/run.py
```
Then you can login using link http://localhost:5000 and `admin:admin` creds.

### Docker

Pull image from Docker Hub:
```
# docker pull ipeacocks/ansibletasker
```
And simply run it:
```
# docker run -d -p 5000:5000 ipeacocks/ansibletasker
```
Thats all, only copying private key remains:
```
# docker cp ~/.ssh/id_rsa container_id:/app/ansible
```
That's it. Login using link http://localhost:5000 and `admin:admin` creds.
