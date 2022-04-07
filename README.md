# infrastructure
AWS infrastructure
Setting up AWS Infrastructure

Steps:
1. Create Administrator user & Administrator Group for the aws account you are working for. Link: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-prereqs.html
2. Install the AWS CLI
3. Windows machine: add aws.exe path to account variables.
4. Generate the Access ID and Access Secret key for the admin user.
5. Run command to generate a stack using cloud formation :
6. export AWS_PROFILE=demo
aws ec2 import-key-pair --key-name "DevInstanceKey" --public-key-material fileb://DevInstanceKey.pem
DEV
aws cloudformation create-stack --stack-name webserviceStack5 --template-body file://csye6225-infra.yml --parameter ParameterKey=MyImageParameter,ParameterValue="ami-049a9b875d82152e2" ParameterKey=KeyPairParameter,ParameterValue="DevInstancekey" ParameterKey=DomainNameParameter,ParameterValue="dev.bhatiadi.me" ParameterKey=hostedZoneID,ParameterValue="Z01096722S5OIW7NXF70F" --capabilities CAPABILITY_NAMED_IAM
DEMO
aws cloudformation create-stack --stack-name webserviceStack5 --template-body file://csye6225-infra.yml --parameter ParameterKey=MyImageParameter,ParameterValue="ami-049a9b875d82152e2" ParameterKey=KeyPairParameter,ParameterValue="DemoKeyPair" ParameterKey=DomainNameParameter,ParameterValue="demo.bhatiadi.me" ParameterKey=hostedZoneID,ParameterValue="Z07744191EL8Q6DDK8QVQ" --capabilities CAPABILITY_NAMED_IAM

Deleting stack
aws s3 rm s3://52e7e710.dev.bhatiadi.me --recursive

Creating policies for Ci/Cd User (DEV)
aws cloudformation create-stack --stack-name cicdstack --template-body file://csye6225-cicd-policy-creation.yml --parameter ParameterKey=AwsAccountIdParameter,ParameterValue="105634846355" ParameterKey=CodeDeployApplicationNameParameter,ParameterValue="csye6225-webapp" ParameterKey=CodeDeployGroupNameParameter,ParameterValue="csye6225-webapp-deployment"  --capabilities CAPABILITY_NAMED_IAM

Creating policies for Ci/Cd User (DEMO)
aws cloudformation create-stack --stack-name cicdstack --template-body file://csye6225-cicd-policy-creation.yml --parameter ParameterKey=AwsAccountIdParameter,ParameterValue="406472615172" ParameterKey=CodeDeployApplicationNameParameter,ParameterValue="csye6225-webapp" ParameterKey=CodeDeployGroupNameParameter,ParameterValue="csye6225-webapp-deployment"  --capabilities CAPABILITY_NAMED_IAM

  
1.  In order to delete a stack, run command 
2.  aws cloudformation delete-stack --stack-name stackAdmin5

