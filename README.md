Ansible Playbook to
- provision an EC2-instance with custom storage configuration
- run fio tests
- transfer results to S3 bucket

Requires Ansible and Boto

1. Clone repository "git clone https://github.com/jkuhlenkamp/fioebs/"  
2. Export Credentials "export AWS_ACCESS_KEY_ID=xxx" "export AWS_SECRET_ACCESS_KEY=xxx"  
3. Adapt "fiobs/exp/env.yml"  
3.1 Choose workload job file  
3.2 Adapt the AWS settings: aws_group_id, aws_vpc_subnet_id, aws_region, aws_instance_type, aws_image_id, aws_instance_number, aws_tag_prefix  
3.3 Adapt the storage configuration  

4. Start playbook
	-> ansible-playbook -i inv/ site.yml --private-key=/Users/jk/jk_f_2015.pem --extra-vars="aws_access_key_id=$AWS_ACCESS_KEY_ID aws_secret_access_key=$AWS_SECRET_ACCESS_KEY"
	
