

## Installation

### Install Ansible

Follow the steps relevant to your OS here: https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html

For Ubuntu:

```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

## Install boto3

```
sudo apt-get install software-properties-common
sudo apt-add-repository universe
sudo apt-get update
sudo apt-get install python3-pip
sudo apt-get install python3-boto3
```

### Install the collection for SSM

To connect to EC2 instances via AWS Systems Manager

```
ansible-galaxy collection install community.aws
```

## AWS Credentials

1. Navigate to your SSO sigin in page
2. Click on "Access Keys" next to the Profie you'd like to use
3. Copy the credentials block in to your AWS credentials file ( usually located at (~/.aws/credentials) )
4. Call the profile `[production]` or update the `aws_profile` variable in playbook.yml to match

## Run the Playbook

Add the instance ID to the `ansible_aws_ssm_instance_id` variable in the playbook.yml file.

The the playbook using:


```
ansible-playbook playbook.yml
```
