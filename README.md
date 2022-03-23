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

aws cloudformation create-stack --stack-name webserviceStack1 --template-body file://csye6225-infra.yml --parameter ParameterKey=MyImageParameter,ParameterValue="ami-04bb5f6f2218efa75" ParameterKey=accesskey,ParameterValue="AKIAV5I5H4UCF2IXNDLL" ParameterKey=secretkey,ParameterValue="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" --capabilities CAPABILITY_NAMED_IAM

Deleting stack
aws s3 rm s3://52e7e710.dev.bhatiadi.me --recursive
1.  
2.  In order to delete a stack, run command 
3.  aws cloudformation delete-stack --stack-name stackAdmin5

