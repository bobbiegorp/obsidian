**c1z7dfpz01 Amaxon ECS service using a single AZ** -> only gives failed check on acceptance, where it says its running in one AZ. For prd it says it's running in 2 AZs, no idea why, because as far as I can see it has the same setup. Anyway, we don't need this multi AZ setup, because our container does not need to be highly available.


**f2iK5R6Dep Amazon RDS Multi-AZ** ->  40% extra costs for multi AZ setup  (db.r6g.xlarge 0.504$ /H -> db.m6g.xlarge 0.704$ /H ). Worth it?


**Hs4Ma3G118 The VPC default security group should not allow inbound and outbound traffic** -> Unused SG in unused VPC. Deleted so should be solved now.


**Hs4Ma3G125 API Gateway should be associated with a WAF Web ACL** -> Need to add WAF to management API, example cdk pattern: https://github.com/cdk-patterns/serverless/blob/main/the-waf-apigateway/README.md


*IN BRANCH* Hs4Ma3G127 API Gateway REST and WebSocket API execution logging should be enabled -> Add stageprops https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_apigateway.StageProps.html


*IN BRANCH*  **Hs4Ma3G160 + Hs4Ma3G161 IAM authentication on RDS**: Add iam_authentication=True to cluster construct. Also change instances=1 to use writer instead. Instances and instance_props are deprecated.


Hs4Ma3G169 S3 permissions granted to other AWS accounts in bucket policies should be restricted: Fixed (all old buckets that are now deleted).


Hs4Ma3G173 S3 Block Public Access setting should be enabled at the bucket-level: Should be fixed (all buckets deleted or public access blocked)


*IN BRANCH* Hs4Ma3G184 Application and Classic Load Balancers logging should be enabled: Need to add access logs configuration to CDK https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_elasticloadbalancingv2.ApplicationLoadBalancer.html#logwbraccesswbrlogsbucket-prefix


Hs4Ma3G185 IAM customer managed policies that you create should not allow wildcard actions for services:
arn:aws:iam::278600615770:policy/service-role/AWSCodePipelineServiceRole-eu-west-1-postnl-businessportal-vpc-dev -> unknown app in quicksight test account, looks like it was built by kouros.pechlivanidis and it is a service role for codepipeline for Elastic beanstalk. There are also s3 buckets and glue scripts related to this postnl-business-portal 
Check with Sjuul and possibly Kouros
Other items were fixed


*IN BRANCH*  Hs4Ma3G190 RDS clusters should have deletion protection enabled: Simple flag to activate deletion protection https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_rds.DatabaseCluster.html (fix together with **Hs4Ma3G160 + Hs4Ma3G161 IAM authentication on RDS**)


Hs4Ma3G193 & Hs4Ma3G191 RDS encryption: These will be annoying. Existing databases cannot be encrypted, meaning we'd have to create a new database and migrate the data over. Maybe we should do this after creating the new billing solution? Then the database size will be much smaller.


*IN BRANCH* Hs4Ma3G199 Database logging should be enabled: needs to be configured in cdk together with Hs4Ma3G190, Hs4Ma3G160 and Hs4Ma3G161. https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_rds.DatabaseCluster.html#cloudwatchlogsexports


Hs4Ma3G235 Amazon ECR private repositories should have tag immutability enabled:



Hs4Ma3G242 Amazon ECR private repositories should have image scanning enabled:



Hs4Ma3G271 API Gateway routes should specify an authorization type: ManagementAppHttpApi = Django CEM app. Don't know much about this setup yet to be able to say to we can solve it.


Hs4Ma3G278 Access logging should be configured for API Gateway V2 Stages:  ManagementAppHttpApi = Django CEM app. Seems like this is not easily done with CDK -> https://www.kevinwmcconnell.com/cdk/http-api-logs-with-cdk


Hs4Ma3G176 ACM certificates should be renewed after a specified time period: removed expired certificates. Should be solved now.


