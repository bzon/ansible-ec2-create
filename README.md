## General Usage
### Run using the latest launch_ami playbook

ansible-playbook launch_ami_v2.yml --extra-vars "instance_name='${ENVIRONMENT}_fmw_docker_host' aws_region=${AWS_REGION} key_name=${AWS_KEY_PAIR} vpc_subnet_id=${AWS_SUBNET_ID} ami_id=${AWS_AMI_ID} instance_type=${INSTANCE_TYPE} volume_size=200 vpc_id=${AWS_VPC_ID}"
