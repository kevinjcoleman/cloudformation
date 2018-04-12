## Create a stack
`aws cloudformation create-stack --stack-name myteststack --template-body file://$(pwd)/basic-ec2.yml --parameters ParameterKey=KeyPair,ParameterValue=ec2-keys`

## Validate a stack template 
`aws cloudformation validate-template --template-url file://$(pwd)/basic-ec2.yml`

## List stacks
`aws cloudformation list-stacks`

### Filter stacks 
`aws cloudformation list-stacks --stack-status-filter ROLLBACK_COMPLETE`

## List stack events 
`aws cloudformation describe-stack-events myteststack`

## Update Stack 
`aws cloudformation update-stack --stack-name eb-teststack-8 --template-body file://$(pwd)/basic-eb.yml`

## Delete a stack 
`aws cloudformation delete-stack --stack-name myteststack`


# Helpful commands 

### SSH into es instance.
`ssh -i ~/.ssh/new-ec2-keys.pem ec2-user@#{url}.us-west-1.compute.amazonaws.com`

### Connect to docker on instance 
`sudo docker COMMAND`

### Check unexpected quit logs 
`cd /var/log/eb-docker/containers/eb-current-app/`
`sudo gzip -d unexpected-quit.log1521345661.gz`
`cat unexpected-quit.log1521345661`


### Check free mem
`free -m`
`grep MemTotal /proc/meminfo`

### Check eb logs 
`cat /var/log/eb-activity.log`



# Notes 

- Need to add custom tcp rule to security group so that port :9200 is open to public, this will need to be closed for actual dev instances in the future though.
- Figure out why access denied is happening for volume mounts.