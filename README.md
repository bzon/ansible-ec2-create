## Overview

This is a playbook that uses ec2 modules to create AWS EC2 instances and security groups. 

## General Usage

Run using version 2 launch_ami playbook

>export EC2_ACCESS_KEY=Your AWS Account Access Key

>export EC2_SECRET_KEY=Your AWS Account Secret Key

>ansible-playbook provision.yml --extra-vars "instance_name='${ENVIRONMENT}_fmw_docker_host' aws_region=${AWS_REGION} key_name=${AWS_KEY_PAIR} vpc_subnet_id=${AWS_SUBNET_ID} ami_id=${AWS_AMI_ID} instance_type=${INSTANCE_TYPE} volume_size=200 vpc_id=${AWS_VPC_ID}"  

The playbook will generate a file called instance_ids.txt which contains the instance id of the provisioned EC2. This is intended for the below playbook to be accepted as a parameter and delete the said instance.

To delete the instance you just provisioned. Run the following:

>ansible-playbook terminate_instances.yml
