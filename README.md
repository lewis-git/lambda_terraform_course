# Notes
## AWS
### Region: 
  - For this project I am using Singapore ~ ap-southeast-1
  - Following the same naming standards from course for simplicity

### RDS:
  - MySQL instance password - WwjdMtaVPyky5X9wGhfj
  - Endpoint - mysqlinstance.chkw00uiseju.ap-southeast-1.rds.amazonaws.com

### Lambda:
  - Important for the code to be region & database agnostic, so it can be carried across various regions no issue
  - Follow Python coding standards, these can be found *** GIT repo
  - Always include error handling, eg. Attempting to turn off an already off RDS instance we don't want it to cause failure

### Terraform:
#### Install:
  - Binaries placing under Program Files, setup the enviornment variable <PATH>
  - VSC Plugin
#### AWS:
  - IAM user - lambda-tf-user
    - Access key 1: AKIAS252WA5HHEW3ADGP 
    - Secret key: **********************************JyJ
#### Hints:
  - For existing or manually created resources, run a Terraform Import so that the tool is aware of the resource Eg. terraform import aws_cloudwatch_log_group.rds_manager "/aws/lambda/rds_manager-ap-southeast-1"
  - Never run "terraform init -reconfigure" loses the state of AWS resources, requiring imports.

## Follow up / Tweaks required

#### Lambda Function
  - Not currently stopping the RDS Instance despite being "Available" issue with Code?
  - Play around with versioning and testing Changes without impacting $LATEST

#### Terraform 
  - Using a deprecated resource "inline_policy" to specify the policy file within the aws_iam_role resource block



    