# ansible-ee

ansible-ee simply say as container with your working environment which mean you don't have to install the dependecies in to your local machine.

### Prerequisite
- **Python3.12**
- **Docker**

### Setup python virtual environment
```shell
python3 -m venv .venv
```
### Activate python virtual environment
```shell
source .venv/bin/activate
```

### Install the requirement
```shell
pip install -r requirements.txt
```

### Run the setup script
```shell
sudo chmod +x ./setup_environment.sh
bash ./setup_environment.sh
```

### Build the execute environment image
```shell
ansible-builder build -f execution-environment.yml -t infra-ee:latest --container-runtime docker -v 3
```

### Run a test with ansible-playbook
```shell
ansible-navigator run playbook.yml --eei infra-ee:latest --mode stdout 
```
