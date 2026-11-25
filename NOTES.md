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
None
None
{"Type":"Notification","MessageId":"6eada195-75c8-42f7-9d81-4fd90a97e30b","TopicArn":"arn:aws:sns:us-east-1:000000000000:my-super-group-alerts","Timestamp":"2026-11-25T12:36:00.551Z","Subject":"ALARM: \"my-super-group-errors\"","Message":"{\"AlarmName\":\"my-super-group-errors\",\"AlarmDescription\":null,\"AWSAccountId\":\"000000000000\",\"AlarmConfigurationUpdatedTimestamp\":\"2026-11-25T12:35:27.000+0000\",\"NewStateValue\":\"ALARM\",\"NewStateReason\":\"Threshold Crossed: 1 datapoint(s) breaching the threshold.\",\"StateChangeTime\":\"2026-11-25T12:36:00.000+0000\",\"Region\":\"US East (N. Virginia)\",\"AlarmArn\":\"arn:aws:cloudwatch:us-east-1:000000000000:alarm:my-super-group-errors\",\"OldStateValue\":\"INSUFFICIENT_DATA\",\"OKActions\":[],\"AlarmActions\":[\"arn:aws:sns:us-east-1:000000000000:my-super-group-alerts\"],\"InsufficientDataActions\":[],\"Trigger\":{\"MetricName\":\"Errors\",\"Namespace\":\"my-super-group\",\"StatisticType\":\"Statistic\",\"Statistic\":\"SUM\",\"Unit\":null,\"Dimensions\":[],\"Period\":60,\"EvaluationPeriods\":1,\"ComparisonOperator\":\"GreaterThanOrEqualToThreshold\",\"Threshold\":1.0,\"TreatMissingData\":null,\"EvaluateLowSampleCountPercentile\":\"\"}}","SignatureVersion":"1","Signature":"DkcE36CmtkJrCz3DRNI9XW3nuU0jHkW23ZBS8xhUORZ6G3K/Q9eDREAbmjA/ULqW1KWmFYouNenZkCeiGLkxydkLgNS0wjZUNvkroiSQcFakYwl+L4I3qUbIlcmyRUvzUsy7if9DhPgM9Kw4+CyiofV23rPPHziaV13M34UgLJ+CgXGa3dxWpGCs4jxpcrtUicthfbx3OslxO5weJ9x1jvVUPz/BuREmAL5Lif46qrvcmM7woIOG5Agh7c4XyT4Bx5rahP3z2CgqxacfPbGc/bAWefVkqQpc2i90J7STxVla3L9abm+BiwaITU5IVYwh4Lj2rZIr8oSf9VmnCOgJkw==","SigningCertURL":"http://localhost:4566/_aws/sns/SimpleNotificationService-593d4f70531abad77510b4ebcf9882a5.pem","UnsubscribeURL":"http://localhost:4566/?Action=Unsubscribe&SubscriptionArn=arn:aws:sns:us-east-1:000000000000:my-super-group-alerts:f90abf64-ff53-4273-a1e9-eb8e2bc107f4","MessageAttributes":{}}
## deployer proof

aws: [ERROR]: An error occurred (AccessDenied) when calling the DeleteDBInstance operation: User is not authorized to perform: rds:DeleteDBInstance
PASS M3 secret my-super-group/db-password exists
PASS M3 the running task gets the password from Secrets Manager
PASS M3 no password in clear in the task definition
PASS M3 an execution role, not admin
PASS M3 app logs land in CloudWatch (/ecs/my-super-group-app)
PASS M3 an alarm pages the my-super-group-alerts topic
PASS M3 the topic delivers to an SQS pager
PASS M3 a paged alarm saved in NOTES.md
PASS M3 deployer role without wildcard actions
PASS M3 deployer AccessDenied proof saved in NOTES.md
PASS M3 no password left in your current scripts
