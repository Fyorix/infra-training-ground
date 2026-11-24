# Group notes

Group: gXX · Members: A, B, C · App: <git URL of the app you deploy>

Write every decision here with one line of why. It becomes your defense pitch.

## M0, setup + IAM
- check output:
- AccessDenied proof:

## M1, compute + data
- check output:

aws: [ERROR]: An error occurred (AccessDenied) when calling the CreateBucket operation: User is not authorized to perform: s3:CreateBucket
PASS M0 Floci reachable
PASS M0 one IAM user per member (found 3)
PASS M0 read-only auditor user exists
PASS M0 auditor denied proof saved in NOTES.md
PASS M0 group bucket exists
PASS M1 app image in ECR
PASS M1 ECS service running (1 task)
PASS M1 ALB answers 200
PASS M1 RDS Postgres available
PASS M1 S3 status page online
PASS M1 infra/deploy.sh committed
PASS M2 VPC my-super-group-vpc exists
PASS M2 2 public subnets (route to IGW)
PASS M2 2 private subnets (route to NAT)
PASS M2 ALB in the public subnets
FAIL M2 ALB answers 200
PASS M2 app service in the private subnets
PASS M2 app tasks without public IP
PASS M2 VPC my-super-group-vpc exists
PASS M2 2 public subnets (route to IGW)
PASS M2 2 private subnets (route to NAT)
PASS M2 ALB in the public subnets
FAIL M2 ALB answers 200
PASS M2 app service in the private subnets
PASS M2 app tasks without public IP
PASS M2 app security group not open to 0.0.0.0/0
PASS M2 database in the VPC, not public
PASS M2 database only reachable from the app's group
PASS M2 intruder blocked from the app
PASS M2 naive deploy deleted (no public DB, no service outside the VPC)
