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
`aws cloudformation update-stack --stack-name myteststack --template-body file://$(pwd)/basic-ec2.yml`

## Delete a stack 
`aws cloudformation delete-stack --stack-name myteststack`