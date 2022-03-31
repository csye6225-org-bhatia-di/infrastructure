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
aws cloudformation create-stack --stack-name webserviceStack5 --template-body file://csye6225-infra.yml --parameter ParameterKey=MyImageParameter,ParameterValue="ami-003aceb1e55fe8166" ParameterKey=KeyPairParameter,ParameterValue="DevInstancekey" ParameterKey=DomainNameParameter,ParameterValue="dev.bhatiadi.me" ParameterKey=hostedZoneID,ParameterValue="Z01096722S5OIW7NXF70F" --capabilities CAPABILITY_NAMED_IAM

Deleting stack
aws s3 rm s3://52e7e710.dev.bhatiadi.me --recursive

Creating policies for Ci/Cd User (DEMO)
aws cloudformation create-stack --stack-name cicdstack --template-body file://csye6225-cicd-policy-creation.yml --parameter ParameterKey=AwsAccountIdParameter,ParameterValue="105634846355" ParameterKey=CodeDeployApplicationNameParameter,ParameterValue="csye6225-webapp" --capabilities CAPABILITY_NAMED_IAM

  
1.  In order to delete a stack, run command 
2.  aws cloudformation delete-stack --stack-name stackAdmin5

