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
7.  
8. aws cloudformation create-stack --stack-name stackAdmin5 --template-body file://csye6225-infra.yml --parameter ParameterKey=VirtualPrivateCloudCIDRParameter,ParameterValue="10.0.0.0/16" ParameterKey=subnetAParameter,ParameterValue="10.0.13.0/24" ParameterKey=subnetBParameter,ParameterValue="10.0.12.0/24" ParameterKey=subnetCParameter,ParameterValue="10.0.11.0/24" ParameterKey=privateSubnetAParameter,ParameterValue="10.0.4.0/24" ParameterKey=privateSubnetBParameter,ParameterValue="10.0.5.0/24" ParameterKey=privateSubnetCParameter,ParameterValue="10.0.6.0/24" ParameterKey=MyImageParameter,ParameterValue="ami-04e68f263c5f75a8e" --capabilities CAPABILITY_NAMED_IAM


aws cloudformation create-stack --stack-name myFirstStack5 --template-body file://csye6225-infra.yml --parameter ParameterKey=ImageValue,ParameterValue="ami-04e68f263c5f75a8e" --capabilities CAPABILITY_NAMED_IAM
9.  
10. In order to delete a stack, run command 
11. aws cloudformation delete-stack --stack-name stackAdmin5

