# powerpipe_module_soc2
A Powerpipe mod is a portable, versioned collection of related Powerpipe resources such as dashboards, benchmarks, queries, and controls. Powerpipe mods and mod resources are defined in HCL, and distributed as simple text files. Modules can be found on the Powerpipe Hub and may be shared with others from any public git repository.

pre-requisite
-HCL [hashicorp language]
-Postgres database
-mysql

-linux machine [currently we are using]


use below link to create dashboard
https://powerpipe.io/docs/powerpipe-hcl/dashboard

# WE ARE CREATING CONTOLLER CALLED SOC2 IN GCP

### install power pipe 
step 1:sudo /bin/sh -c "$(curl -fsSL https://powerpipe.io/install/powerpipe.sh)"
step 2:powerpipe -v  #CHECK VERSION
step 3:powerpipe help # HELP

### install steampipe [Steampipe provides zero-ETL (Extract, Transform, Load) tools for fetching data directly from APIs and services. Steampipe is offered in several distributions:]
step 1:sudo /bin/sh -c "$(curl -fsSL https://steampipe.io/install/steampipe.sh)"
step 2:steampipe -v
step 3:steampipe plugin install steampipe

### 

> .help
Welcome to Steampipe shell.

To start, simply enter your SQL query at the prompt:

  select * from aws_iam_user

Common commands:

.help     Show steampipe help                           
.inspect  View connections, tables & column information 
.exit     Exit from steampipe terminal                  

Advanced commands:

.autocomplete on|off Enable or disable auto-completion                                                            
.cache [mode]        Enable, disable or clear the query cache                                                     
.cache_ttl           Set the cache ttl (time-to-live)                                                             
.clear               Clear the console                                                                            
.connections         List active connections                                                                      
.header on|off       Enable or disable column headers                                                             
.multi on|off        Enable or disable multiline mode                                                             
.output [mode]       Set output format: csv, json, table or line                                                  
.quit                Exit from steampipe terminal                                                                 
.search_path         Display the current search path, or set the search-path by passing in a comma-separated list 
.search_path_prefix  Set a prefix to the current search-path                                                      
.separator           Set csv output separator                                                                     
.tables              List or describe tables                                                                      
.timing [mode]       Enable or disable query execution timing                                                     

Documentation available at https://steampipe.io/docs


### Run your first query...
steampipe query "select name from steampipe_registry_plugin;"
### Result:
```
+----------------------------+
| name                       |
+----------------------------+
| turbot/azuredevops         |
| theapsgroup/vsphere        |
| turbot/ipstack             |
| turbot/hubspot             |
| turbot/bitbucket           |
| turbot/hypothesis          |
| turbot/datadog             |
| ajmaradiaga/btp            |
| turbot/mastodon            |
| tomba-io/tomba             |
| turbot/ibm                 |
| turbot/buildkite           |
| turbot/digitalocean        |
| turbot/imap                |
| ellisvalentiner/confluence |
| turbot/abuseipdb           |
| turbot/hibp                |
| turbot/chaos               |
| turbot/docker              |
| turbot/dockerhub           |
| turbot/ldap                |
| turbot/chaosdynamic        |
| turbot/aiven               |
| turbot/ipinfo              |
| turbot/databricks          |
| turbot/linear              |
| ellisvalentiner/weatherkit |
| turbot/doppler             |
| turbot/circleci            |
| turbot/azuread             |
| turbot/newrelic            |
| mr-destructive/cohereai    |
| francois2metz/gitguardian  |
| turbot/godaddy             |
| turbot/consul              |
| turbot/awscfn              |
| turbot/algolia             |
| solacelabs/solace          |
| turbot/microsoft365        |
| turbot/code                |
| turbot/alicloud            |
| turbot/net                 |
| turbot/duo                 |
| ip2location/ip2locationio  |
| francois2metz/airtable     |
| turbot/ansible             |
| francois2metz/baleen       |
| turbot/auth0               |
| ernw/openstack             |
| turbot/config              |
| grendel-consulting/kolide  |
| theapsgroup/clickup        |
| turbot/linkedin            |
| francois2metz/freshping    |
| turbot/aws                 |
| turbot/cloudflare          |
| turbot/env0                |
| francois2metz/ovh          |
| turbot/linode              |
| turbot/azure               |
| francois2metz/gandi        |
| francois2metz/scalingo     |
| turbot/mongodbatlas        |
| theapsgroup/freshservice   |
| turbot/namecheap           |
| gabrielsoltz/semgrep       |
| turbot/googledirectory     |
| kaggrwal/bitfinex          |
| turbot/hcloud              |
| turbot/jira                |
| turbot/heroku              |
| turbot/crtsh               |
| turbot/mailchimp           |
| turbot/equinix             |
| jplanckeel/opsgenie        |
| turbot/nomad               |
| turbot/okta                |
| turbot/kubernetes          |
| turbot/googlesheets        |
| turbot/jenkins             |
| theapsgroup/gitlab         |
| turbot/googleworkspace     |
| turbot/hackernews          |
| turbot/guardrails          |
| turbot/launchdarkly        |
| turbot/fly                 |
| turbot/googlesearchconsole |
| turbot/csv                 |
| turbot/github              |
| turbot/jumpcloud           |
| turbot/fastly              |
| marekjalovec/make          |
| turbot/grafana             |
| theapsgroup/vault          |
| turbot/crowdstrike         |
| turbot/oci                 |
| turbot/gcp                 |
| turbot/exec                |
| theapsgroup/keycloak       |
| turbot/finance             |
| turbot/tailscale           |
| turbot/sentry              |
| turbot/twitter             |
| turbot/trello              |
| turbot/zoom                |
| turbot/terraform           |
| turbot/snowflake           |
| turbot/splunk              |
| turbot/trivy               |
| turbot/onepassword         |
| turbot/tfe                 |
| turbot/steampipecloud      |
| turbot/updown              |
| turbot/openai              |
| turbot/stripe              |
| turbot/turbot              |
| turbot/servicenow          |
| turbot/twilio              |
| turbot/steampipe           |
| turbot/uptimerobot         |
| turbot/supabase            |
| turbot/slack               |
| turbot/openapi             |
| turbot/shopify             |
| turbot/shodan              |
| turbot/virustotal          |
| turbot/whois               |
| turbot/workos              |
| turbot/wiz                 |
| turbot/openshift           |
| turbot/prometheus          |
| turbot/vanta               |
| turbot/vercel              |
| turbot/zendesk             |
| turbot/panos               |
| turbot/pagerduty           |
| turbot/pipes               |
| turbot/reddit              |
| turbot/salesforce          |
| turbot/urlscan             |
| turbot/planetscale         |
| turbot/scaleway            |
| turbot/rss                 |
------------------------------
```
# installing plugin and using query in steampipe

### Explore
Steampipe provides commands that allow you to discover and explore the tables and data without leaving the query shell. (Of course, this information is all available in the hub if online docs are more your speed...
 https://hub.steampipe.io/plugins/turbot/aws/tables )

Let's fire up Steampipe! Run steampipe query to open an interactive query session:

![image](https://github.com/user-attachments/assets/e478d5aa-1fe5-4def-acf4-469787437596)

Now run the .tables meta-command to list the available tables:

![image](https://github.com/user-attachments/assets/cfc0c377-bd58-44f8-83b1-1abe67ffe27e)

As you can see, there are quite a few tables available in the AWS plugin!

It looks like there's an aws_iam_role table - let's run .inspect to see what's in that table:

![image](https://github.com/user-attachments/assets/10d04e0e-dd98-4d35-8987-915adfdd66e8)


![image](https://github.com/user-attachments/assets/5e7ab3ca-5c54-46fb-82ae-761f6adf3c36)

using query in iam
![image](https://github.com/user-attachments/assets/6bc3f9d5-f9f9-4431-adfe-a197a25d7910)

![image](https://github.com/user-attachments/assets/95cc92bb-2b81-43d8-97bc-d2ab2f173567)

What's Next?
We've merely scratched the surface of what you can do with Steampipe!

Discover more plugins on the Steampipe Hub →
Run dashboards and benchmarks with Powerpipe →
Build workflows as code with Flowpipe →

# GCP controller
https://hub.steampipe.io/plugins/turbot/gcp

prerequisite
-GCP Account

Item	Description
Credentials	When running locally, you must configure your Application Default Credentials. If you are running in Cloud Shell or Cloud Code, the tool uses the credentials you provided when you logged in, and manages any authorizations required.
Permissions	Assign the Viewer role to your user or service account. You may also need additional permissions related to IAM policies, like pubsub.subscriptions.getIamPolicy, pubsub.topics.getIamPolicy, storage.buckets.getIamPolicy, since these are not included in the Viewer role. You can grant these by creating a custom role in your project.
Radius	Each connection represents a single GCP project.
Resolution	1. Credentials from the JSON file specified by the credentials parameter in your steampipe config.
2. Credentials from the JSON file specified by the GOOGLE_APPLICATION_CREDENTIALS environment variable.
3. Credentials from the default JSON file location (~/.config/gcloud/application_default_credentials.json).
4. Credentials from the metadata server

# soc2 detail of aws
This document outlines the **SOC 2 Controls Mapping** for various AWS services and best practices to ensure compliance with security, availability, processing integrity, confidentiality, and privacy principles. Below are the key criteria and controls relevant to each COSO Principle under the SOC 2 framework:

### CC1: Common Criteria Related to Control Environment
**CC1.3 COSO Principle 3:**  
Management establishes, with board oversight, structures, reporting lines, and appropriate authorities and responsibilities in the pursuit of objectives.
- **IAM Group Management:**
  - IAM groups should have at least one user.
  - IAM groups, users, and roles should not have any inline policies.
  - IAM AWS managed policies should be attached to IAM roles.
  - IAM policies should not have statements with admin access.
  - IAM policies should be in use.
  - IAM users should be in at least one group.
  - IAM users should not have any inline or attached policies.
  - IAM user credentials that have not been used in 90 days should be disabled.
- **RDS DB Instances:**
  - RDS DB instances should have IAM authentication enabled.

### CC2: Common Criteria Related to Communication and Information
**CC2.1 COSO Principle 13:**  
The entity obtains or generates and uses relevant, quality information to support the functioning of internal control.
- **S3 Buckets and CloudTrail:**
  - All S3 buckets should log S3 data events in CloudTrail.
  - At least one trail should be enabled with security best practices.
  - AWS Config should be enabled.

### CC3: Common Criteria Related to Risk Assessment
**CC3.1 COSO Principle 6:**  
The entity specifies objectives with sufficient clarity to enable the identification and assessment of risks relating to objectives.
- AWS Config, GuardDuty, and AWS Security Hub should be enabled.

**CC3.2 COSO Principle 7:**  
The entity identifies risks to the achievement of its objectives across the entity and analyzes risks as a basis for determining how the risks should be managed.
- **EC2 Instances:**
  - EC2 instances should be managed by AWS Systems Manager.
  - GuardDuty should be enabled.
  - GuardDuty findings should be archived.
  - IAM users with console access should have MFA enabled.
  - SSM managed instance associations should be compliant.
  - SSM managed instance patching should be compliant.

**CC3.4 COSO Principle 9:**  
The entity identifies and assesses changes that could significantly impact the system of internal control.
- AWS Config should be enabled.

### CC4: Monitoring Activities
**CC4.2 COSO Principle 17:**  
The entity evaluates and communicates internal control deficiencies in a timely manner to those parties responsible for taking corrective action, including senior management and the board of directors, as appropriate.
- CloudWatch alarm action should be enabled.
- GuardDuty should be enabled.
- GuardDuty findings should be archived.

### CC6: Logical and Physical Access
**CC6.1:**  
The entity implements logical access security software, infrastructure, and architectures over protected information assets to protect them from security events to meet the entity's objectives.
- **ACM and Encryption:**
  - ACM certificates should not expire within 30 days.
  - API Gateway stage cache encryption at rest should be enabled.
  - CloudTrail trail logs should be encrypted with KMS CMK.
  - DMS replication instances should not be publicly accessible.
  - Attached EBS volumes should have encryption enabled.
  - EBS snapshots should not be publicly restorable.
  - EBS default encryption should be enabled.
  - EC2 instances should be in a VPC and should not have a public IP address.
  - EC2 instances should be managed by AWS Systems Manager.
  - EFS file system encryption at rest should be enabled.
  - ELB application load balancers should drop HTTP headers and redirect HTTP requests to HTTPS.
  - ELB application load balancers should have Web Application Firewall (WAF) enabled.
  - ELB classic load balancers should use SSL certificates and only use SSL or HTTPS listeners.
  - EMR cluster Kerberos should be enabled.
  - EMR cluster master nodes should not have public IP addresses.
  - ES domain encryption at rest should be enabled and domains should be in a VPC.
  - Elasticsearch domain node-to-node encryption should be enabled.
  - IAM password policies for users should have strong configurations.
  - IAM groups should have at least one user.
  - IAM groups, users, and roles should not have any inline policies.
  - IAM policy should not have statements with admin access.
  - IAM root user should not have access keys.
  - IAM user access keys should be rotated at least every 90 days.
  - IAM users should be in at least one group.
  - IAM user should not have any inline or attached policies.
  - IAM user credentials that have not been used in 90 days should be disabled.
  - KMS keys should not be pending deletion.
  - Lambda functions should be in a VPC and restrict public access.
  - Log group encryption at rest should be enabled.
  - RDS DB instance encryption at rest should be enabled and prohibit public access.
  - RDS DB snapshots should be encrypted at rest and prohibit public access.
  - Redshift cluster encryption in transit should be enabled, and clusters should prohibit public access.
  - S3 bucket default encryption should be enabled, enforce SSL, enable logging, and object lock.
  - S3 bucket policy should prohibit public access, including public read and write access.
  - S3 public access should be blocked at account level.
  - SageMaker endpoint configuration encryption should be enabled.
  - SageMaker notebook instances should not have direct internet access and should have encryption enabled.
  - Secrets Manager secrets should have automatic rotation enabled and rotated as per the schedule.
  - SNS topics should be encrypted at rest.
  - SSM managed instance associations should be compliant.
  - VPC default security group should not allow inbound and outbound traffic.
  - VPC EIPs should be associated with an EC2 instance or ENI.
  - VPC security groups should be associated with at least one ENI.
  - VPC security groups should restrict ingress access on ports 20, 21, 22, 3306, 3389, 4333 from 0.0.0.0/0 and restrict ingress SSH access from 0.0.0.0/0.

**CC6.2:**  
Prior to issuing system credentials and granting system access, the entity registers and authorizes new internal and external users whose access is administered by the entity.
- Similar controls as listed in CC6.1 apply, focusing on certificate expiration, encryption at rest, and public accessibility.

**CC6.3:**  
The entity authorizes, modifies, or removes access to data, software, functions, and other protected information assets based on roles, responsibilities, or the system design and changes, giving consideration to the concepts of least privilege and segregation of duties, to meet the entity’s objectives.
- EMR cluster Kerberos should be enabled.
- IAM groups should have at least one user.
- IAM groups, users, and roles should not have any inline policies.
- IAM AWS managed policies should be attached to IAM roles.
- IAM policy should not have statements with admin access.
- IAM root user should not have access keys.
- IAM users should be in at least one group.
- IAM user should not have any inline or attached policies.
- IAM user credentials that have not been used in 90 days should be disabled.
- S3 bucket policy should prohibit public access.

**CC6.6:**  
The entity implements logical access security measures to protect against threats from sources outside its system boundaries.
- **DMS and Encryption:**
  - DMS replication instances should not be publicly accessible.
  - EBS snapshots should not be publicly restorable.
  - EC2 instances should be in a VPC and should not have a public IP address.
  - ELB application load balancers should have Web Application Firewall (WAF) enabled.
  - EMR cluster master nodes should not have public IP addresses.
  - ES domains should be in a VPC.
  - GuardDuty should be enabled.
  - IAM root user hardware MFA should be enabled.
  - IAM root user MFA should be enabled.
  - IAM users with console access should have MFA enabled.
  - IAM user MFA should be enabled.
  - Lambda functions should be in a VPC and restrict public access.
  - RDS DB instances should prohibit public access.
  - RDS snapshots should prohibit public access.
  - Redshift clusters should prohibit public access.
  - S3 bucket policy should prohibit public access.
  - S3 buckets should prohibit public read and write access.
  - S3 public access should be blocked at account level.
  - SageMaker notebook instances should not have direct internet access.
  - AWS Security Hub should be enabled for an AWS Account.
  - VPC default security group should not allow inbound and outbound traffic.
  - VPC flow logs should be enabled.
  - VPC internet gateways should be attached to authorized VPC.
  - VPC security groups should restrict ingress access on ports 20, 21, 22, 3306, 3389, 4333 from 0.0.0.0/0 and restrict ingress SSH access from 0.0.0.0/0.
  - VPC security groups should restrict ingress TCP and UDP access from 0.0.0.0/0.

**CC6.7:**  
The entity restricts the transmission, movement, and removal of information to authorized internal and external users and processes and protects it during transmission, movement, or removal to meet the entity’s objectives.
- **Encryption and Security Measures:**
  - ACM certificates should not expire within 

30 days.
  - CloudTrail trail logs should be encrypted with KMS CMK.
  - DMS replication instances should not be publicly accessible.
  - EBS snapshots should not be publicly restorable.
  - EFS file system encryption at rest should be enabled.
  - ELB application load balancers should drop HTTP headers and redirect HTTP requests to HTTPS.
  - ELB application load balancers should have Web Application Firewall (WAF) enabled.
  - ELB classic load balancers should use SSL certificates and only use SSL or HTTPS listeners.
  - EMR cluster Kerberos should be enabled.
  - EMR cluster master nodes should not have public IP addresses.
  - ES domain encryption at rest should be enabled and domains should be in a VPC.
  - IAM root user hardware MFA should be enabled.
  - IAM users with console access should have MFA enabled.
  - Lambda functions should be in a VPC and restrict public access.
  - RDS DB instance encryption at rest should be enabled and prohibit public access.
  - RDS snapshots should be encrypted at rest and prohibit public access.
  - Redshift cluster encryption in transit should be enabled, and clusters should prohibit public access.
  - S3 bucket default encryption should be enabled, enforce SSL, enable logging, and object lock.
  - S3 bucket policy should prohibit public access, including public read and write access.
  - S3 public access should be blocked at account level.
  - Secrets Manager secrets should have automatic rotation enabled and rotated as per the schedule.
  - VPC default security group should not allow inbound and outbound traffic.
  - VPC flow logs should be enabled.

---

The outlined SOC 2 controls mapping provides a comprehensive framework for ensuring compliance and security across AWS services. By adhering to these controls, organizations can maintain a robust security posture, protect sensitive data, and ensure the integrity and availability of their systems.

```bash
AWS_Compliance_Benchmarks/
└── SOC_2/
    ├── CC1_Common_Criteria_Related_to_Control_Environment/
    │   ├── CC1.3_COSO_Principle_3_Management_Structures_Reporting_Lines/
    │   │   ├── IAM_Groups/
    │   │   │   ├── IAM_Groups_Should_Have_At_Least_One_User.txt
    │   │   │   ├── IAM_Groups_Users_Roles_No_Inline_Policies.txt
    │   │   │   ├── IAM_Users_At_Least_One_Group.txt
    │   │   │   └── IAM_Users_No_Inline_Or_Attached_Policies.txt
    │   │   ├── IAM_Policies/
    │   │   │   ├── IAM_Policies_No_Admin_Access_Statements.txt
    │   │   │   ├── IAM_Policies_In_Use.txt
    │   │   │   └── IAM_AWS_Managed_Policies_Attached.txt
    │   │   └── IAM_Users/
    │   │       ├── IAM_Users_Credentials_Disabled_After_90_Days.txt
    │   │       └── RDS_DB_Instances_IAM_Authentication_Enabled.txt
    └── CC2_Common_Criteria_Related_to_Communication_and_Information/
        ├── CC2.1_COSO_Principle_13_Quality_Information/
        │   ├── S3_Buckets/
        │   │   └── S3_Buckets_Log_S3_Data_Events_in_CloudTrail.txt
        │   ├── CloudTrail/
        │   │   └── At_Least_One_Trail_Enabled_With_Security_Best_Practices.txt
        │   └── AWS_Config/
            └── AWS_Config_Enabled.txt
AWS_Compliance_Benchmarks/
└── SOC_2/
    ├── CC3_Common_Criteria_Related_to_Risk_Assessment/
    │   ├── CC3.1_COSO_Principle_6_Clarity_of_Objectives/
    │   │   ├── AWS_Config_Enabled.txt
    │   │   ├── GuardDuty_Enabled.txt
    │   │   └── AWS_Security_Hub_Enabled.txt
    │   ├── CC3.2_COSO_Principle_7_Identification_and_Management_of_Risks/
    │   │   ├── EC2_Instances_Managed_by_AWS_Systems_Manager.txt
    │   │   ├── GuardDuty_Enabled.txt
    │   │   ├── GuardDuty_Findings_Archived.txt
    │   │   ├── IAM_Users_With_Console_Access_Have_MFA_Enabled.txt
    │   │   ├── SSM_Managed_Instance_Associations_Compliant.txt
    │   │   └── SSM_Managed_Instance_Patching_Compliant.txt
    │   └── CC3.4_COSO_Principle_9_Impact_of_Changes/
    │       └── AWS_Config_Enabled.txt
    └── CC4_Monitoring_Activities/
        ├── CC4.2_COSO_Principle_17_Communication_of_Control_Deficiencies/
        │   ├── CloudWatch_Alarm_Action_Enabled.txt
        │   ├── GuardDuty_Enabled.txt
        │   └── GuardDuty_Findings_Archived.txt
AWS_Compliance_Benchmarks/
└── SOC_2/
    └── CC6_Logical_and_Physical_Access/
        ├── ACM_Certificates/
        │   └── ACM_Certificates_Expiration_Within_30_Days.txt
        ├── API_Gateway/
        │   └── API_Gateway_Stage_Cache_Encryption_At_Rest_Enabled.txt
        ├── CloudTrail/
        │   └── CloudTrail_Trail_Logs_Encrypted_With_KMS_CMK.txt
        ├── DMS/
        │   └── DMS_Replication_Instances_Not_Publicly_Accessible.txt
        ├── EBS/
        │   ├── Attached_EBS_Volumes_Encryption_Enabled.txt
        │   ├── EBS_Snapshots_Not_Publicly_Restorable.txt
        │   └── EBS_Default_Encryption_Enabled.txt
        ├── EC2/
        │   ├── EC2_Instances_In_VPC.txt
        │   ├── EC2_Instances_No_Public_IP_Address.txt
        │   ├── EC2_Instances_Managed_By_AWS_Systems_Manager.txt
        │   └── EC2_Instances_SSM_Associations_Compliant.txt
        ├── EFS/
        │   └── EFS_File_System_Encryption_At_Rest_Enabled.txt
        ├── ELB/
        │   ├── ELB_Application_Load_Balancers_Drop_HTTP_Headers.txt
        │   ├── ELB_Application_Load_Balancers_Redirect_HTTP_to_HTTPS.txt
        │   ├── ELB_Application_Load_Balancers_WAF_Enabled.txt
        │   ├── ELB_Classic_Load_Balancers_SSL_Certificates.txt
        │   └── ELB_Classic_Load_Balancers_SSL_HTTPS_Listeners_Only.txt
        ├── EMR/
        │   ├── EMR_Cluster_Kerberos_Enabled.txt
        │   └── EMR_Cluster_Master_Nodes_No_Public_IP_Address.txt
        ├── ES/
        │   ├── ES_Domain_Encryption_At_Rest_Enabled.txt
        │   ├── ES_Domains_In_VPC.txt
        │   └── ES_Domain_Node_To_Node_Encryption_Enabled.txt
        ├── IAM/
        │   ├── IAM_Password_Policies_Strong_Configurations.txt
        │   ├── IAM_Groups_Have_At_Least_One_User.txt
        │   ├── IAM_Groups_Users_Roles_No_Inline_Policies.txt
        │   ├── IAM_Policy_No_Admin_Access_Statements.txt
        │   ├── IAM_Root_User_No_Access_Keys.txt
        │   ├── IAM_User_Access_Keys_Rotated_Every_90_Days.txt
        │   ├── IAM_Users_In_At_Least_One_Group.txt
        │   ├── IAM_User_No_Inline_Attached_Policies.txt
        │   ├── IAM_User_Credentials_Not_Used_90_Days_Disabled.txt
        │   └── IAM_Users_Have_MFA_Enabled.txt
        ├── KMS/
        │   └── KMS_Keys_Not_Pending_Deletion.txt
        ├── Lambda/
        │   ├── Lambda_Functions_In_VPC.txt
        │   └── Lambda_Functions_Restrict_Public_Access.txt
        ├── Logs/
        │   ├── Log_Group_Encryption_At_Rest_Enabled.txt
        │   └── CloudWatch_Alarm_Action_Enabled.txt
        ├── RDS/
        │   ├── RDS_DB_Instance_Encryption_At_Rest_Enabled.txt
        │   ├── RDS_DB_Instances_Not_Publicly_Accessible.txt
        │   ├── RDS_DB_Snapshots_Encrypted_At_Rest.txt
        │   └── RDS_Snapshots_Not_Publicly_Accessible.txt
        ├── Redshift/
        │   ├── Redshift_Cluster_Encryption_In_Transit_Enabled.txt
        │   ├── Redshift_Cluster_Audit_Logging_And_Encryption_Enabled.txt
        │   └── Redshift_Clusters_Not_Publicly_Accessible.txt
        ├── S3/
        │   ├── S3_Bucket_Default_Encryption_Enabled.txt
        │   ├── S3_Buckets_Enforce_SSL.txt
        │   ├── S3_Bucket_Logging_Enabled.txt
        │   ├── S3_Bucket_Object_Lock_Enabled.txt
        │   ├── S3_Bucket_Policy_Prohibit_Public_Access.txt
        │   ├── S3_Buckets_Prohibit_Public_Read_Access.txt
        │   ├── S3_Buckets_Prohibit_Public_Write_Access.txt
        │   └── S3_Public_Access_Blocked_At_Account_Level.txt
        ├── SageMaker/
        │   ├── SageMaker_Endpoint_Configuration_Encryption_Enabled.txt
        │   ├── SageMaker_Notebook_Instances_No_Direct_Internet_Access.txt
        │   └── SageMaker_Notebook_Instance_Encryption_Enabled.txt
        ├── Secrets_Manager/
        │   ├── Secrets_Manager_Secrets_Automatic_Rotation_Enabled.txt
        │   └── Secrets_Manager_Secrets_Rotated_As_Per_Rotation_Schedule.txt
        ├── SNS/
        │   └── SNS_Topics_Encrypted_At_Rest.txt
        └── VPC/
            ├── VPC_Default_Security_Group_No_Inbound_Outbound_Traffic.txt
            ├── VPC_EIPs_Associated_With_EC2_Instance_ENI.txt
            ├── VPC_Security_Groups_Associated_With_ENI.txt
            ├── VPC_Security_Groups_Restrict_Ingress_Access_Ports.txt
            └── VPC_Security_Groups_Restrict_Ingress_SSH_Access.txt
SOC2_Controls/
├── CC6.2_Registration_and_Authorization/
│   ├── ACM_Certificates_Expiration.txt
│   ├── API_Gateway_Cache_Encryption.txt
│   ├── CloudTrail_Logs_Encryption.txt
│   ├── DMS_Replication_Instances_Public_Access.txt
│   ├── EBS_Volumes_Encryption.txt
│   ├── EBS_Snapshots_Public_Restore.txt
│   ├── EBS_Default_Encryption.txt
│   ├── EC2_Instances_VPC.txt
│   ├── EC2_Instances_No_Public_IP.txt
│   ├── EC2_Instances_Managed_By_SSM.txt
│   ├── EFS_Encryption.txt
│   ├── ELB_ALB_HTTP_Headers.txt
│   ├── ELB_ALB_HTTP_to_HTTPS_Redirection.txt
│   ├── ELB_ALB_WAF_Enabled.txt
│   ├── ELB_Classic_Load_Balancers_SSL.txt
│   ├── ELB_Classic_Load_Balancers_SSL_Only.txt
│   ├── EMR_Kerberos_Enabled.txt
│   ├── EMR_Master_Nodes_No_Public_IP.txt
│   ├── ES_Domain_Encryption.txt
│   ├── ES_Domains_In_VPC.txt
│   ├── ES_Node_To_Node_Encryption.txt
│   ├── IAM_Password_Policies_Strong.txt
│   ├── IAM_Groups_At_Least_One_User.txt
│   ├── IAM_No_Inline_Policies.txt
│   ├── IAM_No_Admin_Access.txt
│   ├── IAM_Root_User_No_Access_Keys.txt
│   ├── IAM_Access_Keys_Rotation.txt
│   ├── IAM_Users_In_Groups.txt
│   ├── IAM_No_Inline_Or_Attached_Policies.txt
│   ├── IAM_Credentials_Not_Used_Disabled.txt
│   ├── KMS_Keys_Not_Pending_Deletion.txt
│   ├── Lambda_In_VPC.txt
│   ├── Lambda_Restrict_Public_Access.txt
│   ├── Log_Group_Encryption.txt
│   ├── RDS_DB_Encryption.txt
│   ├── RDS_DB_No_Public_Access.txt
│   ├── RDS_Snapshots_Encryption.txt
│   ├── RDS_Snapshots_No_Public_Access.txt
│   ├── Redshift_Cluster_Encryption_In_Transit.txt
│   ├── Redshift_Cluster_Audit_Logging_Encryption.txt
│   ├── Redshift_Clusters_No_Public_Access.txt
│   ├── S3_Bucket_Default_Encryption.txt
│   ├── S3_Buckets_Enforce_SSL.txt
│   ├── S3_Bucket_Logging.txt
│   ├── S3_Bucket_Object_Lock.txt
│   ├── S3_Bucket_Policy_No_Public_Access.txt
│   ├── S3_Buckets_No_Public_Read_Access.txt
│   ├── S3_Buckets_No_Public_Write_Access.txt
│   ├── S3_Public_Access_Blocked.txt
│   ├── SageMaker_Endpoint_Configuration_Encryption.txt
│   ├── SageMaker_No_Direct_Internet_Access.txt
│   ├── SageMaker_Notebook_Encryption.txt
│   ├── Secrets_Manager_Automatic_Rotation.txt
│   ├── Secrets_Manager_Rotation_Schedule.txt
│   ├── SNS_Topics_Encryption.txt
│   ├── SSM_Managed_Instance_Associations.txt
│   ├── VPC_Default_Security_Group.txt
│   ├── VPC_EIPs_Association.txt
│   ├── VPC_Security_Groups_ENI_Association.txt
│   ├── VPC_Security_Groups_Restrict_Ingress.txt
│   ├── VPC_Security_Groups_Restrict_Ingress_SSH.txt
│   ├── VPC_Security_Groups_Restrict_Ingress_TCP_UDP.txt
├── CC6.3_Authorization_Modification_Removal/
│   ├── EMR_Kerberos_Enabled.txt
│   ├── IAM_Groups_At_Least_One_User.txt
│   ├── IAM_No_Inline_Policies.txt
│   ├── IAM_AWS_Managed_Policies.txt
│   ├── IAM_No_Admin_Access.txt
│   ├── IAM_Root_User_No_Access_Keys.txt
│   ├── IAM_Users_In_Groups.txt
│   ├── IAM_No_Inline_Or_Attached_Policies.txt
│   ├── IAM_Credentials_Not_Used_Disabled.txt
│   ├── S3_Bucket_Policy_No_Public_Access.txt
SOC2_Controls/
├── CC6_Logical_and_Physical_Access/
│   ├── DMS_Replication_Instances_No_Public_Access.txt
│   ├── EBS_Snapshots_No_Public_Restore.txt
│   ├── EC2_Instances_In_VPC.txt
│   ├── EC2_Instances_No_Public_IP.txt
│   ├── ELB_ALB_WAF_Enabled.txt
│   ├── EMR_Master_Nodes_No_Public_IP.txt
│   ├── ES_Domains_In_VPC.txt
│   ├── GuardDuty_Enabled.txt
│   ├── IAM_Root_User_Hardware_MFA_Enabled.txt
│   ├── IAM_Root_User_MFA_Enabled.txt
│   ├── IAM_Users_MFA_Enabled.txt
│   ├── Lambda_In_VPC.txt
│   ├── Lambda_Restrict_Public_Access.txt
│   ├── RDS_DB_Instances_No_Public_Access.txt
│   ├── RDS_Snapshots_No_Public_Access.txt
│   ├── Redshift_Clusters_No_Public_Access.txt
│   ├── S3_Bucket_Policy_No_Public_Access.txt
│   ├── S3_Buckets_No_Public_Read_Access.txt
│   ├── S3_Buckets_No_Public_Write_Access.txt
│   ├── S3_Public_Access_Blocked.txt
│   ├── SageMaker_No_Direct_Internet_Access.txt
│   ├── AWS_Security_Hub_Enabled.txt
│   ├── VPC_Default_Security_Group.txt
│   ├── VPC_Flow_Logs_Enabled.txt
│   ├── VPC_Internet_Gateways_Attached.txt
│   ├── VPC_Security_Groups_Restrict_Ingress.txt
│   ├── VPC_Security_Groups_Restrict_Ingress_SSH.txt
│   ├── VPC_Security_Groups_Restrict_Ingress_TCP_UDP.txt
├── CC6_Transmission_Movement_Removal/
│   ├── ACM_Certificates_Expiration.txt
│   ├── API_Gateway_Cache_Encryption.txt
│   ├── CloudFront_Encryption_In_Transit.txt
│   ├── ELB_ALB_HTTP_Headers.txt
│   ├── ELB_ALB_HTTP_to_HTTPS_Redirection.txt
│   ├── ELB_Classic_Load_Balancers_SSL.txt
│   ├── Elasticsearch_Domain_Node_To_Node_Encryption.txt
│   ├── Redshift_Cluster_Encryption_In_Transit.txt
├── CC6_Introduction_of_Unauthorized_Software/
│   └── (Document details or procedures for software control, if available)
├── CC7_System_Operations/
│   ├── CC7.1_Detection_and_Monitoring/
│   │   ├── EC2_Instances_Managed_By_SSM.txt
│   │   ├── GuardDuty_Enabled.txt
│   │   ├── AWS_Security_Hub_Enabled.txt
│   │   ├── SSM_Managed_Instance_Associations_Compliant.txt
│   ├── CC7.2_Monitoring_and_Anomalies/
│   │   ├── API_Gateway_Stage_Logging_Enabled.txt
│   │   ├── Multi_Region_AWS_CloudTrail_Present.txt
│   │   ├── S3_Data_Events_Logged_in_CloudTrail.txt
│   │   ├── Enabled_Trail_in_Region.txt
│   │   ├── CloudTrail_Integration_With_CloudWatch.txt
│   │   ├── CloudWatch_Alarm_Action_Configured.txt
│   │   ├── Log_Group_Retention_365_Days.txt
│   │   ├── CodeBuild_Project_No_Sensitive_Values.txt
│   │   ├── CodeBuild_Repo_OAuth.txt
│   │   ├── EC2_Detailed_Monitoring_Enabled.txt
│   │   ├── ELB_Logging_Enabled.txt
│   │   ├── Lambda_Concurrent_Execution_Limit.txt
│   │   ├── Lambda_Dead_Letter_Queue_Configured.txt
│   │   ├── Database_Logging_Enabled.txt
│   │   ├── Redshift_Audit_Logging_Encryption_Enabled.txt
│   │   ├── S3_Bucket_Logging_Enabled.txt
│   │   ├── AWS_Security_Hub_Enabled.txt
│   │   ├── VPC_Flow_Logs_Enabled.txt
│   │   ├── WAF_Web_ACL_Logging_Enabled.txt
│   │   ├── WAFv2_ACL_Logging_Enabled.txt
│   ├── CC7.3_Evaluating_Security_Events/
│   │   ├── API_Gateway_Stage_Logging_Enabled.txt
│   │   ├── CloudTrail_Integration_With_CloudWatch.txt
│   │   ├── CloudTrail_Trail_Log_File_Validation_Enabled.txt
│   │   ├── CloudWatch_Alarm_Action_Configured.txt
│   │   ├── Log_Group_Retention_365_Days.txt
│   │   ├── ELB_Logging_Enabled.txt
│   │   ├── Elasticsearch_Domain_Logs_To_CloudWatch.txt
│   │   ├── GuardDuty_Enabled.txt
│   │   ├── GuardDuty_Findings_Archived.txt
│   │   ├── Lambda_Dead_Letter_Queue_Configured.txt
│   │   ├── Log_Group_Encryption_At_Rest.txt
│   │   ├── OpenSearch_Domains_Audit_Logging_Enabled.txt
│   │   ├── OpenSearch_Domains_Logs_To_CloudWatch.txt
│   │   ├── Database_Logging_Enabled.txt
│   │   ├── Redshift_Audit_Logging_Enabled.txt
│   │   ├── S3_Bucket_Event_Notifications_Enabled.txt
│   │   ├── S3_Bucket_Logging_Enabled.txt
│   │   ├── AWS_Security_Hub_Enabled.txt
│   │   ├── VPC_Flow_Logs_Enabled.txt
│   │   ├── WAF_Web_ACL_Logging_Enabled.txt
SOC2_Controls/
├── CC7_System_Operations/
│   ├── CC7.4_Response_to_Security_Incidents/
│   │   ├── Backup_Plan_Min_Frequency_and_Retention_Check.txt
│   │   ├── Backup_Recovery_Points_Encrypted.txt
│   │   ├── Backup_Recovery_Points_Manual_Deletion_Disabled.txt
│   │   ├── Backup_Recovery_Points_No_Expiration_Before_Retention_Period.txt
│   │   ├── CloudWatch_Alarm_Action_Configured.txt
│   │   ├── DynamoDB_Tables_In_Backup_Plan.txt
│   │   ├── DynamoDB_Table_Point_In_Time_Recovery_Enabled.txt
│   │   ├── DynamoDB_Tables_Protected_By_Backup_Plan.txt
│   │   ├── EBS_Volumes_In_Backup_Plan.txt
│   │   ├── EBS_Volumes_Protected_By_Backup_Plan.txt
│   │   ├── EC2_Instance_EBS_Optimization_Enabled.txt
│   │   ├── EC2_Instances_Protected_By_Backup_Plan.txt
│   │   ├── EFS_File_Systems_In_Backup_Plan.txt
│   │   ├── EFS_File_Systems_Protected_By_Backup_Plan.txt
│   │   ├── ElastiCache_Redis_Cluster_Automatic_Backup_Enabled_15_Days_or_Greater.txt
│   │   ├── FSx_File_System_Protected_By_Backup_Plan.txt
│   │   ├── GuardDuty_Enabled.txt
│   │   ├── GuardDuty_Findings_Archived.txt
│   │   ├── Lambda_Functions_Dead_Letter_Queue_Configured.txt
│   │   ├── RDS_Aurora_Clusters_Protected_By_Backup_Plan.txt
│   │   ├── RDS_DB_Instance_Backup_Enabled.txt
│   │   ├── RDS_DB_Instances_In_Backup_Plan.txt
│   │   ├── RDS_DB_Instance_Protected_By_Backup_Plan.txt
│   │   ├── AWS_Redshift_Clusters_Automatic_Snapshots_Enabled.txt
│   │   ├── S3_Bucket_Cross_Region_Replication_Enabled.txt
│   │   ├── S3_Bucket_Versioning_Enabled.txt
│   │   ├── AWS_Security_Hub_Enabled.txt
├── CC8_Change_Management/
│   ├── CC8.1_Change_Authorization_and_Implementation/
│   │   ├── CodeBuild_Project_No_Sensitive_Values.txt
│   │   ├── CodeBuild_Repo_OAuth.txt
│   │   ├── AWS_Config_Enabled.txt
├── A1_Additional_Criteria_for_Availability/
│   ├── A1.2_Backup_and_Recovery_Processes/
│   │   ├── API_Gateway_Stage_Logging_Enabled.txt
│   │   ├── Backup_Plan_Min_Frequency_and_Retention_Check.txt
│   │   ├── Backup_Recovery_Points_Encrypted.txt
│   │   ├── Backup_Recovery_Points_Manual_Deletion_Disabled.txt
│   │   ├── Backup_Recovery_Points_No_Expiration_Before_Retention_Period.txt
│   │   ├── Multi_Region_AWS_CloudTrail_Present.txt
│   │   ├── Enabled_Trail_in_Region.txt
│   │   ├── CloudTrail_Trails_Integrated_With_CloudWatch_Logs.txt
│   │   ├── DynamoDB_Tables_In_Backup_Plan.txt
│   │   ├── DynamoDB_Table_Point_In_Time_Recovery_Enabled.txt
│   │   ├── DynamoDB_Tables_Protected_By_Backup_Plan.txt
│   │   ├── EBS_Volumes_In_Backup_Plan.txt
│   │   ├── EBS_Volumes_Protected_By_Backup_Plan.txt
│   │   ├── EC2_Instance_EBS_Optimization_Enabled.txt
│   │   ├── EC2_Instances_Protected_By_Backup_Plan.txt
│   │   ├── EFS_File_Systems_In_Backup_Plan.txt
│   │   ├── EFS_File_Systems_Protected_By_Backup_Plan.txt
│   │   ├── ElastiCache_Redis_Cluster_Automatic_Backup_Enabled_15_Days_or_Greater.txt
│   │   ├── ELB_Application_and_Classic_Load_Balancer_Logging_Enabled.txt
│   │   ├── FSx_File_System_Protected_By_Backup_Plan.txt
│   │   ├── RDS_Aurora_Clusters_Protected_By_Backup_Plan.txt
│   │   ├── RDS_DB_Instance_Backup_Enabled.txt
│   │   ├── RDS_DB_Instances_In_Backup_Plan.txt
│   │   ├── Database_Logging_Enabled.txt
│   │   ├── RDS_DB_Instance_Protected_By_Backup_Plan.txt
│   │   ├── AWS_Redshift_Clusters_Automatic_Snapshots_Enabled.txt
│   │   ├── S3_Bucket_Cross_Region_Replication_Enabled.txt
│   │   ├── S3_Bucket_Versioning_Enabled.txt
│   │   ├── WAF_Web_ACL_Logging_Enabled.txt
│   │   ├── WAFv2_ACL_Logging_Enabled.txt
├── C1_Additional_Criteria_for_Confidentiality/
│   ├── C1.1_Confidential_Information_Identification_and_Maintenance/
│   │   ├── RDS_DB_Instances_Deletion_Protection_Enabled.txt
│   │   ├── S3_Bucket_Object_Lock_Enabled.txt
│   │   ├── S3_Buckets_Versioning_Lifecycle_Policies_Configured.txt
│   ├── C1.2_Disposal_of_Confidential_Information/
│   │   ├── S3_Buckets_Lifecycle_Policies_Configured.txt
│   │   ├── S3_Bucket_Versioning_Enabled.txt
SOC2_Controls/
├── C1_Additional_Criteria_for_Confidentiality/
│   ├── C1.1_Identification_and_Maintenance_of_Confidential_Information/
│   │   ├── RDS_DB_Instances_Deletion_Protection_Enabled.txt
│   │   ├── S3_Bucket_Object_Lock_Enabled.txt
│   │   ├── S3_Buckets_With_Versioning_Lifecycle_Policies_Configured.txt
│   ├── C1.2_Disposal_of_Confidential_Information/
│   │   ├── S3_Buckets_Lifecycle_Policies_Configured.txt
│   │   ├── S3_Bucket_Versioning_Enabled.txt
```

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![image](https://github.com/user-attachments/assets/3f976456-b793-4386-b9d5-209ec258720f)

## AWS to GCP Service Comparison

| **AWS Service**                          | **GCP Service**                          |
|------------------------------------------|------------------------------------------|
| aws_accessanalyzer_analyzer              | gcp_alloydb_cluster                      |
| aws_accessanalyzer_finding               | gcp_alloydb_instance                     |
| aws_account                              | gcp_apikeys_key                          |
| aws_account_alternate_contact            | gcp_app_engine_application               |
| aws_account_contact                      | gcp_artifact_registry_repository         |
| aws_acm_certificate                      | gcp_audit_policy                         |
| aws_acmpca_certificate_authority         | gcp_bigquery_dataset                     |
| aws_amplify_app                          | gcp_bigquery_job                         |
| aws_api_gateway_api_key                  | gcp_bigquery_table                       |
| aws_api_gateway_authorizer               | gcp_bigtable_instance                    |
| aws_api_gateway_domain_name              | gcp_billing_account                      |
| aws_api_gateway_method                   | gcp_billing_budget                       |
| aws_api_gateway_rest_api                 | gcp_cloud_asset                          |
| aws_api_gateway_stage                    | gcp_cloud_identity_group                 |
| aws_api_gateway_usage_plan               | gcp_cloud_identity_group_membership      |
| aws_api_gatewayv2_api                    | gcp_cloud_run_service                    |
| aws_api_gatewayv2_domain_name            | gcp_cloudfunctions_function              |
| aws_api_gatewayv2_integration            | gcp_compute_address                      |
| aws_api_gatewayv2_route                  | gcp_compute_autoscaler                   |
| aws_api_gatewayv2_stage                  | gcp_compute_backend_bucket               |
| aws_appautoscaling_policy                | gcp_compute_backend_service              |
| aws_appautoscaling_target                | gcp_compute_disk                         |
| aws_appconfig_application                | gcp_compute_disk_metric_read_ops         |
| aws_appstream_fleet                      | gcp_compute_disk_metric_read_ops_daily   |
| aws_appstream_image                      | gcp_compute_disk_metric_read_ops_hourly  |
| aws_appsync_graphql_api                  | gcp_compute_disk_metric_write_ops        |
| aws_athena_query_execution               | gcp_compute_disk_metric_write_ops_daily  |
| aws_athena_workgroup                     | gcp_compute_disk_metric_write_ops_hourly |
| aws_auditmanager_assessment              | gcp_compute_firewall                     |
| aws_auditmanager_control                 | gcp_compute_forwarding_rule              |
| aws_auditmanager_evidence                | gcp_compute_global_address               |
| aws_auditmanager_evidence_folder         | gcp_compute_global_forwarding_rule       |
| aws_auditmanager_framework               | gcp_compute_ha_vpn_gateway               |
| aws_availability_zone                    | gcp_compute_image                        |
| aws_backup_framework                     | gcp_compute_instance                     |
| aws_backup_job                           | gcp_compute_instance_group               |
| aws_backup_legal_hold                    | gcp_compute_instance_metric_cpu_utilization |
| aws_backup_plan                          | gcp_compute_instance_metric_cpu_utilization_daily |
| aws_backup_protected_resource            | gcp_compute_instance_metric_cpu_utilization_hourly |
| aws_backup_recovery_point                | gcp_compute_instance_template           |
| aws_backup_report_plan                   | gcp_compute_machine_image               |
| aws_backup_selection                     | gcp_compute_machine_type                |
| aws_backup_vault                         | gcp_compute_network                     |
| aws_cloudcontrol_resource                | gcp_compute_node_group                  |
| aws_cloudformation_stack                 | gcp_compute_node_template               |
| aws_cloudformation_stack_resource        | gcp_compute_project_metadata            |
| aws_cloudformation_stack_set             | gcp_compute_region                      |
| aws_cloudfront_cache_policy              | gcp_compute_resource_policy            |
| aws_cloudfront_distribution              | gcp_compute_route                       |
| aws_cloudfront_function                  | gcp_compute_router                      |
| aws_cloudfront_origin_access_identity    | gcp_compute_snapshot                    |
| aws_cloudfront_origin_request_policy     | gcp_compute_ssl_policy                  |
| aws_cloudfront_response_headers_policy   | gcp_compute_subnetwork                  |
| aws_cloudsearch_domain                   | gcp_compute_target_https_proxy          |
| aws_cloudtrail_channel                   | gcp_compute_target_pool                 |
| aws_cloudtrail_event_data_store          | gcp_compute_target_ssl_proxy            |
| aws_cloudtrail_import                    | gcp_compute_target_vpn_gateway          |
| aws_cloudtrail_lookup_event              | gcp_compute_url_map                     |
| aws_cloudtrail_query                     | gcp_compute_vpn_tunnel                  |
| aws_cloudtrail_trail                     | gcp_compute_zone                        |
| aws_cloudtrail_trail_event               | gcp_dataproc_cluster                    |
| aws_cloudwatch_alarm                     | gcp_dns_managed_zone                    |
| aws_cloudwatch_log_event                 | gcp_dns_policy                          |
| aws_cloudwatch_log_group                 | gcp_dns_record_set                      |
| aws_cloudwatch_log_metric_filter         | gcp_iam_policy                           |
| aws_cloudwatch_log_resource_policy       | gcp_iam_role                             |
| aws_cloudwatch_log_stream                | gcp_kms_key                              |
| aws_cloudwatch_log_subscription_filter   | gcp_kms_key_ring                         |
| aws_cloudwatch_metric                    | gcp_kms_key_version                      |
| aws_cloudwatch_metric_data_point         | gcp_kubernetes_cluster                  |
| aws_cloudwatch_metric_statistic_data_point | gcp_kubernetes_node_pool               |
| aws_codeartifact_domain                  | gcp_logging_bucket                      |
| aws_codeartifact_repository              | gcp_logging_exclusion                   |
| aws_codebuild_build                      | gcp_logging_log_entry                   |
| aws_codebuild_project                    | gcp_logging_metric                      |
| aws_codebuild_source_credential          | gcp_logging_sink                        |
| aws_codecommit_repository                | gcp_monitoring_alert_policy             |
| aws_codedeploy_app                       | gcp_monitoring_group                    |
| aws_codedeploy_deployment_config         | gcp_monitoring_notification_channel     |
| aws_codedeploy_deployment_group          | gcp_organization                        |
| aws_codepipeline_pipeline                | gcp_project                             |
| aws_codestar_notification_rule           | gcp_project_organization_policy         |
| aws_cognito_identity_pool                | gcp_project_service                     |
| aws_cognito_identity_provider            | gcp_pubsub_snapshot                      |
| aws_cognito_user_pool                    | gcp_pubsub_subscription                 |
| aws_config_aggregate_authorization       | gcp_pubsub_topic                         |
| aws_config_configuration_recorder        | gcp_redis_instance                       |
| aws_config_conformance_pack              | gcp_secret_manager_secret                |
| aws_config_retention_configuration       | gcp_service_account                      |
| aws_config_rule                          | gcp_service_account_key                 |
| aws_cost_by_account_daily                | gcp_sql_backup                           |
| aws_cost_by_account_monthly              | gcp_sql_database                         |
| aws_cost_by_record_type_daily            | gcp_sql_database_instance                |
| aws_cost_by_record_type_monthly          | gcp_sql_database_instance_metric_connections |
| aws_cost_by_service_daily                | gcp_sql_database_instance_metric_connections_daily |
| aws_cost_by_service_monthly              | gcp_sql_database_instance_metric_connections_hourly |
| aws_cost_by_service_usage_type_daily     | gcp_sql_database_instance_metric_cpu_utilization |
| aws_cost_by_service_usage_type_monthly   | gcp_sql_database_instance_metric_cpu_utilization_daily |
| aws_cost_by_tag                           | gcp_sql_database_instance_metric_cpu_utilization_hourly |
| aws_cost_forecast_daily                  | gcp_storage_bucket                       |
| aws_cost_forecast_monthly                | gcp_storage_object                       |
| aws_cost_usage                            | gcp_tag_binding                          |
| aws_dax_cluster                           | gcp_vertex_ai_endpoint                   |
| aws_dax_parameter_group                   | gcp_vertex_ai_feature                    |
| aws_dax_subnet_group                      | gcp_vertex_ai_model                      |
| aws_directconnect_connection              | gcp_vertex_ai_model_deployment           |
| aws_directconnect_private_virtual_interface | gcp_vertex_ai_model_metadata          |
| aws_directconnect_public_virtual_interface | gcp_vertex_ai_notebook                 |
| aws_directconnect_transit_virtual_interface | gcp_vertex_ai_pipeline                 |
| aws_dms_endpoint                           | gcp_vertex_ai_tensorboard               |
| aws_dms_event_subscription                | gcp_vertex_ai_training_pipeline         |
| aws_dms_replication_instance              | gcp_vertex_ai_training_pipeline_template |
| aws_dms_replication_task                  | gcp_vpc_network                         |
| aws_dms_replication_task_assessment       | gcp_vpc_network_peering                 |
| aws_dms_source_endpoint                   | gcp_vpc_subnetwork                       |
| aws_dms_target_endpoint                   | gcp_vpn_tunnel                           |
| aws_dynamodb_table                        | gcp_workspace                           |
| aws_dynamodb_table_metric                 | gcp_zone                                 |
| aws_dynamodb_table_stream                 | gcp_zones                                |
-----------------------------------------------------------------------------------------

```
Name: Look for similarly named controls.
Description: Compare descriptions to identify controls that address the same or similar security or compliance concerns.

Manual Matching:

Go through the lists and match controls based on name and description.
Note any controls that are clearly equivalent or closely related.
Automated Tools:

Consider using text comparison tools or scripts to assist with the comparison process.
Tools like diff for Unix-based systems, or online text comparison tools might be helpful.

Spreadsheet Software: Microsoft Excel, Google Sheets.

----------------------------------

now the task that i was assigned is

Task Overview:

You have been assigned to compare and align the controls between AWS and GCP. The goal is to identify matching controls and list them to contribute to the PowerPipe GitHub repository created by Torbot.

Details:

AWS Controls: There are over 400 controls available.
GCP Controls: There are currently 104 controls listed.
Objectives:

Compare Controls:

Identify and match controls between AWS and GCP based on their names and descriptions.
Create a comprehensive list of matched controls.
Contribute to GitHub:

Use the matched controls list to contribute to the PowerPipe GitHub repository, which is maintained by Torbot.
SOC 2 Controls for GCP:

Currently, SOC 2 controls are available for AWS but not for GCP.
You will need to create and add SOC 2 controls for GCP, as this has not been done yet.
Deliverables:

A detailed list of matching controls between AWS and GCP.
Added SOC 2 controls for GCP in the PowerPipe GitHub repository.

------------------------------------------------------------------------


To tackle this task, you can follow these steps to compare and align the controls between AWS and GCP, and contribute to the PowerPipe GitHub repository:

### 1. **Gather Control Lists**

1. **AWS Controls**: Obtain the complete list of AWS controls. If you don’t have it yet, you might be able to find it in AWS documentation or compliance reports.

2. **GCP Controls**: Similarly, gather the list of GCP controls. Check GCP's compliance and security documentation.

### 2. **Create a Comparison Framework**

1. **Define Matching Criteria**:
   - **Name**: Look for similarly named controls.
   - **Description**: Compare descriptions to identify controls that address the same or similar security or compliance concerns.

2. **Build a Mapping Template**:
   - Use a spreadsheet to list AWS controls and their descriptions.
   - Create columns for GCP controls and descriptions to align with AWS controls.

### 3. **Compare Controls**

1. **Manual Matching**:
   - Go through the lists and match controls based on name and description.
   - Note any controls that are clearly equivalent or closely related.

2. **Automated Tools**:
   - Consider using text comparison tools or scripts to assist with the comparison process.
   - Tools like `diff` for Unix-based systems, or online text comparison tools might be helpful.

### 4. **Document Matched Controls**

1. **Create a Comprehensive List**:
   - Document each matched pair of AWS and GCP controls in a clear and structured format.
   - Include details such as control names, descriptions, and any relevant comments.

2. **Prepare for GitHub Contribution**:
   - Ensure the list is formatted according to the repository’s contribution guidelines.

### 5. **Add SOC 2 Controls for GCP**

1. **Identify SOC 2 Controls**:
   - Research SOC 2 compliance requirements and identify relevant controls for GCP.

2. **Create SOC 2 Controls Documentation**:
   - Document SOC 2 controls specific to GCP.
   - Ensure these controls address the same aspects as SOC 2 controls for AWS.

### 6. **Contribute to GitHub**

1. **Prepare Pull Request**:
   - Fork the PowerPipe GitHub repository if you haven't already.
   - Add the matched controls list and SOC 2 controls for GCP to the appropriate files in your fork.

2. **Submit Pull Request**:
   - Create a pull request with a detailed description of the changes and the rationale behind them.
   - Follow any additional guidelines provided by the repository maintainers.

### Sample Spreadsheet Template

| AWS Control Name | AWS Control Description | GCP Control Name | GCP Control Description | Comments |
|------------------|--------------------------|------------------|--------------------------|----------|
| AWS-Control-1    | Description of AWS Control 1 | GCP-Control-1    | Description of GCP Control 1 | Matched based on similar functionality |
| AWS-Control-2    | Description of AWS Control 2 | GCP-Control-2    | Description of GCP Control 2 | Not an exact match but addresses similar concerns |

### Tools and Resources

- **Text Comparison Tools**: `diff`, WinMerge, or online text comparison tools.
- **Spreadsheet Software**: Microsoft Excel, Google Sheets.
- **GitHub**: For contributing and managing pull requests.

If you need help with any specific part of this process, just let me know!
```

```
[completed task]
-finding similarity between aws and gcp and listing them in exel.
 
 
[next tasks]
- i have listed similarities, as per names were matching [accuracy check has not yet complete and few corrections has to be done yet] 

-this above colomn list has to be added, check link " https://github.com/turbot/steampipe-mod-aws-compliance/tree/v0.96/soc_2 " 
in same way gcp soc2 will be created in this repo " https://github.com/rajath-optit/powerpipe_module_soc2/new/main?readme=1 "
 
PS: 
AWS SOC2/: Main directory for SOC 2 compliance benchmarks.
CC1_Control_Environment/: Contains files related to the control environment.
CC2_Communication_Information/: Contains files related to communication and information.
CC3_Risk_Assessment/: Contains files related to risk assessment.
CC4_Monitoring_Activities/: Contains files related to monitoring activities.
CC6_Access_Security/: Contains files related to logical and physical access.
CC7_System_Operations/: Contains files related to system operations.
CC8_Change_Management/: Contains files related to change management.
A1_Availability/: Contains files related to availability.
C1_Confidentiality/: Contains files related to confidentiality.
we create file and use the extension ".sp" which means steampipe has shown in below screenshot. [This hcl code help generate aws complience reports, after sequentially adding required table in side steam pipe template.] 
```

Here are the detailed, step-by-step PowerPipe GitHub repository.
### 1. **Fork the Repository**

1. **Go to the PowerPipe GitHub Repository**:
   - Navigate to the [PowerPipe repository](https://github.com/Torbot/powerpipe) on GitHub.

2. **Fork the Repository**:
   - Click the **Fork** button at the top right corner of the repository page.
   - This creates a copy of the repository under your GitHub account.

### 2. **Clone Your Fork**

1. **Clone the Forked Repository**:
   - Open your terminal or command prompt.
   - Run the following command to clone your fork locally:
     ```bash
     git clone https://github.com/YOUR_USERNAME/powerpipe.git
     ```
   - Replace `YOUR_USERNAME` with your GitHub username.

2. **Navigate to the Repository Directory**:
   - Change directory to the cloned repository:
     ```bash
     cd powerpipe
     ```

### 3. **Create a New Branch**

1. **Create a New Branch**:
   - It’s good practice to create a new branch for your changes. Run:
     ```bash
     git checkout -b compare-controls
     ```

### 4. **Prepare Your Changes**

1. **Add Matched Controls**:
   - Create or update files in your local repository to include the list of matched controls between AWS and GCP.
   - Ensure the formatting aligns with the repository’s guidelines.

2. **Add SOC 2 Controls for GCP**:
   - Document SOC 2 controls for GCP in the repository, following the structure and format of existing SOC 2 controls for AWS.

### 5. **Commit Your Changes**

1. **Stage Your Changes**:
   - Add the files you’ve modified or created:
     ```bash
     git add .
     ```

2. **Commit Your Changes**:
   - Commit your changes with a descriptive message:
     ```bash
     git commit -m "Added matched controls between AWS and GCP and SOC 2 controls for GCP"
     ```

### 6. **Push Your Changes**

1. **Push to Your Fork**:
   - Push the changes to your forked repository on GitHub:
     ```bash
     git push origin compare-controls
     ```

### 7. **Create a Pull Request**

1. **Go to the GitHub Repository**:
   - Navigate back to the PowerPipe repository on GitHub.

2. **Open a Pull Request**:
   - Click the **Pull Requests** tab.
   - Click the **New Pull Request** button.
   - Choose the `compare-controls` branch from your fork as the source branch and the main branch of the original repository as the target branch.
   - Add a title and description for your pull request, summarizing the changes you’ve made and why they are important.

3. **Submit the Pull Request**:
   - Click the **Create Pull Request** button.

### 8. **Follow Up**

1. **Monitor Your Pull Request**:
   - Watch for comments or review requests from the repository maintainers.
   - Respond to feedback or make any necessary changes.

# creating steampipe and generating report in cli
step 1: install and update plugin

![image](https://github.com/user-attachments/assets/af7bfc7d-80cd-4e14-ae50-9f524fe26244)

table
```
> .tables
 ==> aws
+--------------------------------------------------------------+--------------------------------------------------------------------+
| table                                                        | description                                                        |
+--------------------------------------------------------------+--------------------------------------------------------------------+
| aws_accessanalyzer_analyzer                                  | AWS Access Analyzer                                                |
| aws_accessanalyzer_finding                                   | AWS Access Analyzer Finding                                        |
| aws_account                                                  | AWS Account                                                        |
| aws_account_alternate_contact                                | AWS Account Alternate Contact                                      |
| aws_account_contact                                          | AWS Account Contact                                                |
| aws_acm_certificate                                          | AWS ACM Certificate                                                |
| aws_acmpca_certificate_authority                             | AWS ACM Private Certificate Authority                              |
| aws_amplify_app                                              | AWS Amplify App                                                    |
| aws_api_gateway_api_key                                      | AWS API Gateway API Key                                            |
| aws_api_gateway_authorizer                                   | AWS API Gateway Authorizer                                         |
| aws_api_gateway_domain_name                                  | AWS API Gateway Domain Name                                        |
| aws_api_gateway_method                                       | AWS API Gateway Method                                             |
| aws_api_gateway_rest_api                                     | AWS API Gateway Rest API                                           |
| aws_api_gateway_stage                                        | AWS API Gateway Stage                                              |
| aws_api_gateway_usage_plan                                   | AWS API Gateway Usage Plan                                         |
| aws_api_gatewayv2_api                                        | AWS API Gateway Version 2 API                                      |
| aws_api_gatewayv2_domain_name                                | AWS API Gateway Version 2 Domain Name                              |
| aws_api_gatewayv2_integration                                | AWS API Gateway Version 2 Integration                              |
| aws_api_gatewayv2_route                                      | AWS API Gateway Version 2 Route                                    |
| aws_api_gatewayv2_stage                                      | AWS API Gateway Version 2 Stage                                    |
| aws_appautoscaling_policy                                    | AWS Application Auto Scaling Policy                                |
| aws_appautoscaling_target                                    | AWS Application Auto Scaling Target                                |
| aws_appconfig_application                                    | AWS AppConfig Application                                          |
| aws_appstream_fleet                                          | AWS AppStream Fleet                                                |
| aws_appstream_image                                          | AWS AppStream Image                                                |
| aws_appsync_graphql_api                                      | AWS AppSync GraphQL API                                            |
| aws_athena_query_execution                                   | AWS Athena Query Execution                                         |
| aws_athena_workgroup                                         | AWS Athena Workgroup                                               |
| aws_auditmanager_assessment                                  | AWS Audit Manager Assessment                                       |
| aws_auditmanager_control                                     | AWS Audit Manager Control                                          |
| aws_auditmanager_evidence                                    | AWS Audit Manager Evidence                                         |
| aws_auditmanager_evidence_folder                             | AWS Audit Manager Evidence Folder                                  |
| aws_auditmanager_framework                                   | AWS Audit Manager Framework                                        |
| aws_availability_zone                                        | AWS Availability Zone                                              |
| aws_backup_framework                                         | AWS Backup Framework                                               |
| aws_backup_job                                               | AWS Backup Job                                                     |
| aws_backup_legal_hold                                        | AWS Backup Legal Hold                                              |
| aws_backup_plan                                              | AWS Backup Plan                                                    |
| aws_backup_protected_resource                                | AWS Backup Protected Resource                                      |
| aws_backup_recovery_point                                    | AWS Backup Recovery Point                                          |
| aws_backup_report_plan                                       | AWS Backup Report Plan                                             |
| aws_backup_selection                                         | AWS Backup Selection                                               |
| aws_backup_vault                                             | AWS Backup Vault                                                   |
| aws_cloudcontrol_resource                                    | AWS Cloud Control Resource                                         |
| aws_cloudformation_stack                                     | AWS CloudFormation Stack                                           |
| aws_cloudformation_stack_resource                            | AWS CloudFormation Stack Resource                                  |
| aws_cloudformation_stack_set                                 | AWS CloudFormation Stack Set                                       |
| aws_cloudfront_cache_policy                                  | AWS CloudFront Cache Policy                                        |
| aws_cloudfront_distribution                                  | AWS CloudFront Distribution                                        |
| aws_cloudfront_function                                      | AWS CloudFront Function                                            |
| aws_cloudfront_origin_access_identity                        | AWS CloudFront Origin Access Identity                              |
| aws_cloudfront_origin_request_policy                         | AWS CloudFront Origin Request Policy                               |
| aws_cloudfront_response_headers_policy                       | AWS Cloudfront Response Headers Policy                             |
| aws_cloudsearch_domain                                       | AWS CloudSearch Domain                                             |
| aws_cloudtrail_channel                                       | AWS CloudTrail Channel                                             |
| aws_cloudtrail_event_data_store                              | AWS CloudTrail Event Data Store                                    |
| aws_cloudtrail_import                                        | AWS CloudTrail Import                                              |
| aws_cloudtrail_lookup_event                                  | AWS CloudTrail Lookup Event                                        |
| aws_cloudtrail_query                                         | AWS CloudTrail Query                                               |
| aws_cloudtrail_trail                                         | AWS CloudTrail Trail                                               |
| aws_cloudtrail_trail_event                                   | CloudTrail events from cloudwatch service.                         |
| aws_cloudwatch_alarm                                         | AWS CloudWatch Alarm                                               |
| aws_cloudwatch_log_event                                     | AWS CloudWatch Log Event                                           |
| aws_cloudwatch_log_group                                     | AWS CloudWatch Log Group                                           |
| aws_cloudwatch_log_metric_filter                             | AWS CloudWatch Log Metric Filter                                   |
| aws_cloudwatch_log_resource_policy                           | AWS CloudWatch Log Resource Policy                                 |
| aws_cloudwatch_log_stream                                    | AWS CloudWatch Log Stream                                          |
| aws_cloudwatch_log_subscription_filter                       | AWS CloudWatch Log Subscription Filter                             |
| aws_cloudwatch_metric                                        | AWS CloudWatch Metric                                              |
| aws_cloudwatch_metric_data_point                             | AWS CloudWatch Metric Data Point                                   |
| aws_cloudwatch_metric_statistic_data_point                   | AWS CloudWatch Metric Statistic Data Point                         |
| aws_codeartifact_domain                                      | AWS Code Artifact Domain                                           |
| aws_codeartifact_repository                                  | AWS CodeArtifact Repository                                        |
| aws_codebuild_build                                          | AWS CodeBuild Build                                                |
| aws_codebuild_project                                        | AWS CodeBuild Project                                              |
| aws_codebuild_source_credential                              | AWS CodeBuild Source Credential                                    |
| aws_codecommit_repository                                    | AWS CodeCommit Repository                                          |
| aws_codedeploy_app                                           | AWS CodeDeploy Application                                         |
| aws_codedeploy_deployment_config                             | AWS CodeDeploy Deployment Config                                   |
| aws_codedeploy_deployment_group                              | AWS CodeDeploy Deployment Group                                    |
| aws_codepipeline_pipeline                                    | AWS Codepipeline Pipeline                                          |
| aws_codestar_notification_rule                               | AWS CodeStar Notification Rule                                     |
| aws_cognito_identity_pool                                    | AWS Cognito Identity Pool                                          |
| aws_cognito_identity_provider                                | AWS Cognito Identity Provider                                      |
| aws_cognito_user_pool                                        | AWS Cognito User Pool                                              |
| aws_config_aggregate_authorization                           | AWS Config Aggregate Authorization                                 |
| aws_config_configuration_recorder                            | AWS Config Configuration Recorder                                  |
| aws_config_conformance_pack                                  | AWS Config Conformance Pack                                        |
| aws_config_retention_configuration                           | AWS Config Retention Configuration                                 |
| aws_config_rule                                              | AWS Config Rule                                                    |
| aws_cost_by_account_daily                                    | AWS Cost Explorer - Cost by Linked Account (Daily)                 |
| aws_cost_by_account_monthly                                  | AWS Cost Explorer - Cost by Linked Account (Monthly)               |
| aws_cost_by_record_type_daily                                | AWS Cost Explorer - Cost by Record Type (Daily)                    |
| aws_cost_by_record_type_monthly                              | AWS Cost Explorer - Cost by Record Type (Monthly)                  |
| aws_cost_by_service_daily                                    | AWS Cost Explorer - Cost by Service (Daily)                        |
| aws_cost_by_service_monthly                                  | AWS Cost Explorer - Cost by Service (Monthly)                      |
| aws_cost_by_service_usage_type_daily                         | AWS Cost Explorer - Cost by Service and Usage Type (Daily)         |
| aws_cost_by_service_usage_type_monthly                       | AWS Cost Explorer - Cost by Service and Usage Type (Monthly)       |
| aws_cost_by_tag                                              | AWS Cost Explorer - Cost By Tags                                   |
| aws_cost_forecast_daily                                      | AWS Cost Explorer - Cost Forecast (Daily)                          |
| aws_cost_forecast_monthly                                    | AWS Cost Explorer - Cost Forecast (Monthly)                        |
| aws_cost_usage                                               | AWS Cost Explorer - Cost and Usage                                 |
| aws_dax_cluster                                              | AWS DAX Cluster                                                    |
| aws_dax_parameter                                            | AWS DAX Parameter                                                  |
| aws_dax_parameter_group                                      | AWS DAX Parameter Group                                            |
| aws_dax_subnet_group                                         | AWS DAX Subnet Group                                               |
| aws_directory_service_certificate                            | AWS Directory Service Certificate                                  |
| aws_directory_service_directory                              | AWS Directory Service Directory                                    |
| aws_directory_service_log_subscription                       | AWS Directory Service Log Subscription                             |
| aws_dlm_lifecycle_policy                                     | AWS DLM Lifecycle Policy                                           |
| aws_dms_certificate                                          | AWS DMS Certificate                                                |
| aws_dms_endpoint                                             | AWS DMS Endpoint                                                   |
| aws_dms_replication_instance                                 | AWS DMS Replication Instance                                       |
| aws_dms_replication_task                                     | AWS DMS Replication Task                                           |
| aws_docdb_cluster                                            | AWS DocumentDB Cluster                                             |
| aws_docdb_cluster_instance                                   | AWS DocumentDB Cluster Instance                                    |
| aws_docdb_cluster_snapshot                                   | AWS DocumentDB Cluster Snapshot                                    |
| aws_drs_job                                                  | AWS DRS Job                                                        |
| aws_drs_recovery_instance                                    | AWS DRS recovery instance                                          |
| aws_drs_recovery_snapshot                                    | AWS DRS Recovery Snapshot                                          |
| aws_drs_source_server                                        | AWS DRS Source Server                                              |
| aws_dynamodb_backup                                          | AWS DynamoDB Backup                                                |
| aws_dynamodb_global_table                                    | AWS DynamoDB Global Table                                          |
| aws_dynamodb_metric_account_provisioned_read_capacity_util   | AWS DynamoDB Metric Account Provisioned Read Capacity Utilization  |
| aws_dynamodb_metric_account_provisioned_write_capacity_util  | AWS DynamoDB Metric Account Provisioned Write Capacity Utilization |
| aws_dynamodb_table                                           | AWS DynamoDB Table                                                 |
| aws_dynamodb_table_export                                    | AWS DynamoDB Table Export                                          |
| aws_ebs_snapshot                                             | AWS EBS Snapshot                                                   |
| aws_ebs_volume                                               | AWS EBS Volume                                                     |
| aws_ebs_volume_metric_read_ops                               | AWS EBS Volume Cloudwatch Metrics - Read Ops                       |
| aws_ebs_volume_metric_read_ops_daily                         | AWS EBS Volume Cloudwatch Metrics - Read Ops (Daily)               |
| aws_ebs_volume_metric_read_ops_hourly                        | AWS EBS Volume Cloudwatch Metrics - Read Ops (Hourly)              |
| aws_ebs_volume_metric_write_ops                              | AWS EBS Volume Cloudwatch Metrics - Write Ops                      |
| aws_ebs_volume_metric_write_ops_daily                        | AWS EBS Volume Cloudwatch Metrics - Write Ops (Daily)              |
| aws_ebs_volume_metric_write_ops_hourly                       | AWS EBS Volume Cloudwatch Metrics - Write Ops (Hourly)             |
| aws_ec2_ami                                                  | AWS EC2 AMI                                                        |
| aws_ec2_ami_shared                                           | AWS EC2 AMI - All public, private, and shared AMIs                 |
| aws_ec2_application_load_balancer                            | AWS EC2 Application Load Balancer                                  |
| aws_ec2_application_load_balancer_metric_request_count       | AWS EC2 Application Load Balancer Metrics - Request Count          |
| aws_ec2_application_load_balancer_metric_request_count_daily | AWS EC2 Application Load Balancer Metrics - Request Count (Daily)  |
| aws_ec2_autoscaling_group                                    | AWS EC2 Autoscaling Group                                          |
| aws_ec2_capacity_reservation                                 | AWS EC2 Capacity Reservation                                       |
| aws_ec2_classic_load_balancer                                | AWS EC2 Classic Load Balancer                                      |
| aws_ec2_client_vpn_endpoint                                  | AWS EC2 Client VPN Endpoint                                        |
| aws_ec2_gateway_load_balancer                                | AWS EC2 Gateway Load Balancer                                      |
| aws_ec2_instance                                             | AWS EC2 Instance                                                   |
| aws_ec2_instance_availability                                | AWS EC2 Instance Availability                                      |
| aws_ec2_instance_metric_cpu_utilization                      | AWS EC2 Instance Cloudwatch Metrics - CPU Utilization              |
| aws_ec2_instance_metric_cpu_utilization_daily                | AWS EC2 Instance Cloudwatch Metrics - CPU Utilization (Daily)      |
| aws_ec2_instance_metric_cpu_utilization_hourly               | AWS EC2 Instance Cloudwatch Metrics - CPU Utilization (Hourly)     |
| aws_ec2_instance_type                                        | AWS EC2 Instance Type                                              |
| aws_ec2_key_pair                                             | AWS EC2 Key Pair                                                   |
| aws_ec2_launch_configuration                                 | AWS EC2 Launch Configuration                                       |
| aws_ec2_launch_template                                      | AWS EC2 Launch Template                                            |
| aws_ec2_launch_template_version                              | AWS EC2 Launch Template Version                                    |
| aws_ec2_load_balancer_listener                               | AWS EC2 Load Balancer Listener                                     |
| aws_ec2_managed_prefix_list                                  | AWS EC2 Managed Prefix List                                        |
| aws_ec2_managed_prefix_list_entry                            | AWS EC2 Managed Prefix List Entry                                  |
| aws_ec2_network_interface                                    | AWS EC2 Network Interface                                          |
| aws_ec2_network_load_balancer                                | AWS EC2 Network Load Balancer                                      |
| aws_ec2_network_load_balancer_metric_net_flow_count          | AWS EC2 Network Load Balancer Metrics - Net Flow Count             |
| aws_ec2_network_load_balancer_metric_net_flow_count_daily    | AWS EC2 Network Load Balancer Metrics - Net Flow Count (Daily)     |
| aws_ec2_regional_settings                                    | AWS EC2 Regional Settings                                          |
| aws_ec2_reserved_instance                                    | AWS EC2 Reserved Instance                                          |
| aws_ec2_spot_price                                           | AWS EC2 Spot Price History                                         |
| aws_ec2_ssl_policy                                           | AWS EC2 SSL Policy                                                 |
| aws_ec2_target_group                                         | AWS EC2 Target Group                                               |
| aws_ec2_transit_gateway                                      | AWS EC2 Transit Gateway                                            |
| aws_ec2_transit_gateway_route                                | AWS EC2 Transit Gateway Route                                      |
| aws_ec2_transit_gateway_route_table                          | AWS EC2 Transit Gateway Route Table                                |
| aws_ec2_transit_gateway_vpc_attachment                       |                                                                    |
| aws_ecr_image                                                | AWS ECR Image                                                      |
| aws_ecr_image_scan_finding                                   | AWS ECR Image Scan Finding                                         |
| aws_ecr_registry_scanning_configuration                      | AWS ECR Registry Scanning Configuration                            |
| aws_ecr_repository                                           | AWS ECR Repository                                                 |
| aws_ecrpublic_repository                                     | AWS ECR Public Repository                                          |
| aws_ecs_cluster                                              | AWS ECS Cluster                                                    |
| aws_ecs_cluster_metric_cpu_utilization                       | AWS ECS Cluster Cloudwatch Metrics - CPU Utilization               |
| aws_ecs_cluster_metric_cpu_utilization_daily                 | AWS ECS Cluster Cloudwatch Metrics - CPU Utilization (Daily)       |
| aws_ecs_cluster_metric_cpu_utilization_hourly                | AWS ECS Cluster Cloudwatch Metrics - CPU Utilization (Hourly)      |
| aws_ecs_container_instance                                   | AWS ECS Container Instance                                         |
| aws_ecs_service                                              | AWS ECS Service                                                    |
| aws_ecs_task                                                 | AWS ECS Task                                                       |
| aws_ecs_task_definition                                      | AWS ECS Task Definition                                            |
| aws_efs_access_point                                         | AWS EFS Access Point                                               |
| aws_efs_file_system                                          | AWS Elastic File System                                            |
| aws_efs_mount_target                                         | AWS EFS Mount Target                                               |
| aws_eks_addon                                                | AWS EKS Addon                                                      |
| aws_eks_addon_version                                        | AWS EKS Addon Version                                              |
| aws_eks_cluster                                              | AWS Elastic Kubernetes Service Cluster                             |
| aws_eks_fargate_profile                                      | AWS Elastic Kubernetes Service Fargate Profile                     |
| aws_eks_identity_provider_config                             | AWS EKS Identity Provider Config                                   |
| aws_eks_node_group                                           | AWS EKS Node Group                                                 |
| aws_elastic_beanstalk_application                            | AWS Elastic Beanstalk Application                                  |
| aws_elastic_beanstalk_application_version                    | AWS Elastic Beanstalk Application Version                          |
| aws_elastic_beanstalk_environment                            | AWS ElasticBeanstalk Environment                                   |
| aws_elasticache_cluster                                      | AWS ElastiCache Cluster                                            |
| aws_elasticache_parameter_group                              | AWS ElastiCache Parameter Group                                    |
| aws_elasticache_redis_metric_cache_hits_hourly               | AWS Elasticache Redis CacheHits metric (Hourly)                    |
| aws_elasticache_redis_metric_curr_connections_hourly         | AWS Elasticache Redis CurrConnections metric (Hourly)              |
| aws_elasticache_redis_metric_engine_cpu_utilization_daily    | AWS Elasticache Redis EngineCPUUtilization metric (Daily)          |
| aws_elasticache_redis_metric_engine_cpu_utilization_hourly   | AWS Elasticache Redis EngineCPUUtilization metric (Hourly)         |
| aws_elasticache_redis_metric_get_type_cmds_hourly            | AWS Elasticache Redis GetTypeCmds metric(Hourly)                   |
| aws_elasticache_redis_metric_list_based_cmds_hourly          | AWS Elasticache Redis ListBasedCmds metric (Hourly)                |
| aws_elasticache_redis_metric_new_connections_hourly          | AWS Elasticache Redis NewConnections metric (Hourly)               |
| aws_elasticache_replication_group                            | AWS ElastiCache Replication Group                                  |
| aws_elasticache_reserved_cache_node                          | AWS ElastiCache Reserved Cache Node                                |
| aws_elasticache_subnet_group                                 | AWS ElastiCache Subnet Group                                       |
| aws_elasticsearch_domain                                     | AWS Elasticsearch Domain                                           |
| aws_emr_block_public_access_configuration                    | AWS EMR Block Public Access Configuration                          |
| aws_emr_cluster                                              | AWS EMR Cluster                                                    |
| aws_emr_cluster_metric_is_idle                               | AWS EMR Cluster Cloudwatch Metrics - IsIdle                        |
| aws_emr_instance                                             | AWS EMR Instance                                                   |
| aws_emr_instance_fleet                                       | AWS EMR Instance Fleet                                             |
| aws_emr_instance_group                                       | AWS EMR Instance Group                                             |
| aws_emr_security_configuration                               | AWS EMR Security Configuration                                     |
| aws_eventbridge_bus                                          | AWS EventBridge Bus                                                |
| aws_eventbridge_rule                                         | AWS EventBridge Rule                                               |
| aws_fms_app_list                                             | AWS FMS App List                                                   |
| aws_fms_policy                                               | AWS FMS Policy                                                     |
| aws_fsx_file_system                                          | AWS FSx File System                                                |
| aws_glacier_vault                                            | AWS Glacier Vault                                                  |
| aws_globalaccelerator_accelerator                            | AWS Global Accelerator Accelerator                                 |
| aws_globalaccelerator_endpoint_group                         | AWS Global Accelerator Endpoint Group                              |
| aws_globalaccelerator_listener                               | AWS Global Accelerator Listener                                    |
| aws_glue_catalog_database                                    | AWS Glue Catalog Database                                          |
| aws_glue_catalog_table                                       | AWS Glue Catalog Table                                             |
| aws_glue_connection                                          | AWS Glue Connection                                                |
| aws_glue_crawler                                             | AWS Glue Crawler                                                   |
| aws_glue_data_catalog_encryption_settings                    | AWS Glue Data Catalog Encryption Settings                          |
| aws_glue_data_quality_ruleset                                | AWS Glue Data Quality Ruleset                                      |
| aws_glue_dev_endpoint                                        | AWS Glue Dev Endpoint                                              |
| aws_glue_job                                                 | AWS Glue Job                                                       |
| aws_glue_security_configuration                              | AWS Glue Security Configuration                                    |
| aws_guardduty_detector                                       | AWS GuardDuty Detector                                             |
| aws_guardduty_filter                                         | AWS GuardDuty Filter                                               |
| aws_guardduty_finding                                        | AWS GuardDuty Finding                                              |
| aws_guardduty_ipset                                          | AWS GuardDuty IPSet                                                |
| aws_guardduty_member                                         | AWS GuardDuty Member                                               |
| aws_guardduty_publishing_destination                         | AWS GuardDuty Publishing Destination                               |
| aws_guardduty_threat_intel_set                               | AWS GuardDuty ThreatIntelSet                                       |
| aws_health_affected_entity                                   | AWS Health Affected Entity                                         |
| aws_health_event                                             | AWS Health Event                                                   |
| aws_iam_access_advisor                                       | AWS IAM Access Advisor                                             |
| aws_iam_access_key                                           | AWS IAM User Access Key                                            |
| aws_iam_account_password_policy                              | AWS IAM Account Password Policy                                    |
| aws_iam_account_summary                                      | AWS IAM Account Summary                                            |
| aws_iam_action                                               | AWS IAM Action                                                     |
| aws_iam_credential_report                                    | AWS IAM Credential Report                                          |
| aws_iam_group                                                | AWS IAM Group                                                      |
| aws_iam_open_id_connect_provider                             | AWS IAM OpenID Connect Provider                                    |
| aws_iam_policy                                               | AWS IAM Policy                                                     |
| aws_iam_policy_attachment                                    | AWS IAM Policy Attachment                                          |
| aws_iam_policy_simulator                                     | AWS IAM Policy Simulator                                           |
| aws_iam_role                                                 | AWS IAM Role                                                       |
| aws_iam_saml_provider                                        | AWS IAM Saml Provider                                              |
| aws_iam_server_certificate                                   | AWS IAM Server Certificate                                         |
| aws_iam_service_specific_credential                          | AWS IAM User Service Specific Credential                           |
| aws_iam_user                                                 | AWS IAM User                                                       |
| aws_iam_virtual_mfa_device                                   | AWS IAM Virtual MFA device                                         |
| aws_identitystore_group                                      | AWS Identity Store Group                                           |
| aws_identitystore_group_membership                           | AWS Identity Store Group Membership                                |
| aws_identitystore_user                                       | AWS Identity Store User                                            |
| aws_inspector2_coverage                                      | AWS Inspector2 Coverage                                            |
| aws_inspector2_coverage_statistics                           | AWS Inspector2 Coverage Statistics                                 |
| aws_inspector2_finding                                       | AWS Inspector2 Finding                                             |
| aws_inspector2_member                                        | AWS Inspector2 Member                                              |
| aws_inspector_assessment_run                                 | AWS Inspector Assessment Run                                       |
| aws_inspector_assessment_target                              | AWS Inspector Assessment Target                                    |
| aws_inspector_assessment_template                            | AWS Inspector Assessment Template                                  |
| aws_inspector_exclusion                                      | AWS Inspector Exclusion                                            |
| aws_inspector_finding                                        | AWS Inspector Finding                                              |
| aws_iot_fleet_metric                                         | AWS IoT Fleet Metric                                               |
| aws_iot_thing                                                | AWS IoT Thing                                                      |
| aws_iot_thing_group                                          | AWS IoT Thing Group                                                |
| aws_iot_thing_type                                           | AWS IoT Thing Type                                                 |
| aws_kinesis_consumer                                         | AWS Kinesis Consumer                                               |
| aws_kinesis_firehose_delivery_stream                         | AWS Kinesis Firehose Delivery Stream                               |
| aws_kinesis_stream                                           | AWS Kinesis Stream                                                 |
| aws_kinesis_video_stream                                     | AWS Kinesis Video Stream                                           |
| aws_kinesisanalyticsv2_application                           | AWS Kinesis Analytics V2 Application                               |
| aws_kms_alias                                                | AWS KMS Alias                                                      |
| aws_kms_key                                                  | AWS KMS Key                                                        |
| aws_kms_key_rotation                                         | AWS KMS Key Rotation                                               |
| aws_lambda_alias                                             | AWS Lambda Alias                                                   |
| aws_lambda_event_source_mapping                              | AWS Lambda Event Source Mapping                                    |
| aws_lambda_function                                          | AWS Lambda Function                                                |
| aws_lambda_function_metric_duration_daily                    | AWS Lambda Function Cloudwatch Metrics - Duration (Daily)          |
| aws_lambda_function_metric_errors_daily                      | AWS Lambda Function Cloudwatch Metrics - Errors (Daily)            |
| aws_lambda_function_metric_invocations_daily                 | AWS Lambda Function Cloudwatch Metrics - Invocations (Daily)       |
| aws_lambda_layer                                             | AWS Lambda Layer                                                   |
| aws_lambda_layer_version                                     | AWS Lambda Layer Version                                           |
| aws_lambda_version                                           | AWS Lambda Version                                                 |
| aws_lightsail_instance                                       | AWS Lightsail Instance                                             |
| aws_macie2_classification_job                                | AWS Macie2 Classification Job                                      |
| aws_media_store_container                                    | AWS Media Store Container                                          |
| aws_mgn_application                                          | AWS MGN Application                                                |
| aws_mq_broker                                                | AWS MQ Broker                                                      |
| aws_msk_cluster                                              | AWS Managed Streaming for Apache Kafka                             |
| aws_msk_serverless_cluster                                   | AWS Serverless Managed Streaming for Apache Kafka                  |
| aws_neptune_db_cluster                                       | AWS Neptune DB Cluster                                             |
| aws_neptune_db_cluster_snapshot                              | AWS Neptune DB Cluster Snapshot                                    |
| aws_networkfirewall_firewall                                 | AWS Network Firewall Firewall                                      |
| aws_networkfirewall_firewall_policy                          | AWS Network Firewall Policy                                        |
| aws_networkfirewall_rule_group                               | AWS Network Firewall Rule Group                                    |
| aws_oam_link                                                 | AWS OAM Link                                                       |
| aws_oam_sink                                                 | AWS OAM Sink                                                       |
| aws_opensearch_domain                                        | AWS OpenSearch Domain                                              |
| aws_organizations_account                                    | AWS Organizations Account                                          |
| aws_organizations_organizational_unit                        | AWS Organizations Organizational Unit                              |
| aws_organizations_policy                                     | AWS Organizations Policy                                           |
| aws_organizations_policy_target                              | AWS Organizations Policy Target                                    |
| aws_organizations_root                                       | AWS Organizations Root                                             |
| aws_pinpoint_app                                             | AWS Pinpoint App                                                   |
| aws_pipes_pipe                                               | AWS Pipes Pipe                                                     |
| aws_pricing_product                                          | AWS Pricing Product                                                |
| aws_pricing_service_attribute                                | AWS Pricing Service Attribute                                      |
| aws_ram_principal_association                                | AWS RAM Principal Association                                      |
| aws_ram_resource_association                                 | AWS RAM Resource Association                                       |
| aws_rds_db_cluster                                           | AWS RDS DB Cluster                                                 |
| aws_rds_db_cluster_parameter_group                           | AWS RDS DB Cluster Parameter Group                                 |
| aws_rds_db_cluster_snapshot                                  | AWS RDS DB Cluster Snapshot                                        |
| aws_rds_db_engine_version                                    | AWS RDS DB Engine Version                                          |
| aws_rds_db_event_subscription                                | AWS RDS DB Event Subscription                                      |
| aws_rds_db_instance                                          | AWS RDS DB Instance                                                |
| aws_rds_db_instance_automated_backup                         | AWS RDS DB Instance Automated Backup                               |
| aws_rds_db_instance_metric_connections                       | AWS RDS DB Instance Cloudwatch Metrics - DB Connections            |
| aws_rds_db_instance_metric_connections_daily                 | AWS RDS DB Instance Cloudwatch Metrics - DB Connections (Daily)    |
| aws_rds_db_instance_metric_connections_hourly                | AWS RDS DB Instance Cloudwatch Metrics - DB Connections (Hourly)   |
| aws_rds_db_instance_metric_cpu_utilization                   | AWS RDS DB Instance Cloudwatch Metrics - CPU Utilization           |
| aws_rds_db_instance_metric_cpu_utilization_daily             | AWS RDS DB Instance Cloudwatch Metrics - CPU Utilization (Daily)   |
| aws_rds_db_instance_metric_cpu_utilization_hourly            | AWS RDS DB Instance Cloudwatch Metrics - CPU Utilization (Hourly)  |
| aws_rds_db_instance_metric_read_iops                         | AWS RDS DB Instance Cloudwatch Metrics - Read IOPS                 |
| aws_rds_db_instance_metric_read_iops_daily                   | AWS RDS DB Instance Cloudwatch Metrics - Read IOPS (Daily)         |
| aws_rds_db_instance_metric_read_iops_hourly                  | AWS RDS DB Instance Cloudwatch Metrics - Read IOPS (Hourly)        |
| aws_rds_db_instance_metric_write_iops                        | AWS RDS DB Instance Cloudwatch Metrics - Write IOPS                |
| aws_rds_db_instance_metric_write_iops_daily                  | AWS RDS DB Instance Cloudwatch Metrics - Write IOPS (Daily)        |
| aws_rds_db_instance_metric_write_iops_hourly                 | AWS RDS DB Instance Cloudwatch Metrics - Write IOPS (Hourly)       |
| aws_rds_db_option_group                                      | AWS RDS DB Option Group                                            |
| aws_rds_db_parameter_group                                   | AWS RDS DB Parameter Group                                         |
| aws_rds_db_proxy                                             | AWS RDS DB Proxy                                                   |
| aws_rds_db_recommendation                                    | AWS RDS DB Recommendation                                          |
| aws_rds_db_snapshot                                          | AWS RDS DB Snapshot                                                |
| aws_rds_db_subnet_group                                      | AWS RDS DB Subnet Group                                            |
| aws_rds_reserved_db_instance                                 | AWS RDS Reserved DB Instance                                       |
| aws_redshift_cluster                                         | AWS Redshift Cluster                                               |
| aws_redshift_cluster_metric_cpu_utilization_daily            | AWS Redshift Cluster Cloudwatch Metrics - CPU Utilization (Daily)  |
| aws_redshift_event_subscription                              | AWS Redshift Event Subscription                                    |
| aws_redshift_parameter_group                                 | AWS Redshift Parameter Group                                       |
| aws_redshift_snapshot                                        | AWS Redshift Snapshot                                              |
| aws_redshift_subnet_group                                    | AWS Redshift Subnet Group                                          |
| aws_redshiftserverless_namespace                             | AWS Redshift Serverless Namespace                                  |
| aws_redshiftserverless_workgroup                             | AWS Redshift Serverless Workgroup                                  |
| aws_region                                                   | AWS Region                                                         |
| aws_resource_explorer_index                                  | AWS Resource Explorer Index                                        |
| aws_resource_explorer_search                                 | AWS Resource Explorer Search                                       |
| aws_resource_explorer_supported_resource_type                | AWS Resource Explorer Supported Resource Type                      |
| aws_route53_domain                                           | AWS Route53 Domain                                                 |
| aws_route53_health_check                                     | AWS Route53 Health Check                                           |
| aws_route53_query_log                                        | AWS Route53 Query Logging Configuration                            |
| aws_route53_record                                           | AWS Route53 Record                                                 |
| aws_route53_resolver_endpoint                                | AWS Route53 Resolver Endpoint                                      |
| aws_route53_resolver_query_log_config                        | AWS Route53 Resolver Query Logging Configuration                   |
| aws_route53_resolver_rule                                    | AWS Route53 Resolver Rule                                          |
| aws_route53_traffic_policy                                   | AWS Route53 Traffic Policy                                         |
| aws_route53_traffic_policy_instance                          | AWS Route53 Traffic Policy Instance                                |
| aws_route53_vpc_association_authorization                    | AWS Route53 VPC Association Authorization                          |
| aws_route53_zone                                             | AWS Route53 Zone                                                   |
| aws_s3_access_point                                          | AWS S3 Access Point                                                |
| aws_s3_account_settings                                      | AWS S3 Account Block Public Access Settings                        |
| aws_s3_bucket                                                | AWS S3 Bucket                                                      |
| aws_s3_bucket_intelligent_tiering_configuration              | AWS S3 Bucket Intelligent Tiering Configuration                    |
| aws_s3_multi_region_access_point                             | AWS S3 Multi Region Access Point                                   |
| aws_s3_object                                                | List AWS S3 Objects in S3 buckets by bucket name.                  |
| aws_s3_object_version                                        | AWS S3 Object Version                                              |
| aws_sagemaker_app                                            | AWS Sagemaker App                                                  |
| aws_sagemaker_domain                                         | AWS Sagemaker Domain                                               |
| aws_sagemaker_endpoint_configuration                         | AWS Sagemaker Endpoint Configuration                               |
| aws_sagemaker_model                                          | AWS Sagemaker Model                                                |
| aws_sagemaker_notebook_instance                              | AWS Sagemaker Notebook Instance                                    |
| aws_sagemaker_training_job                                   | AWS SageMaker Training Job                                         |
| aws_secretsmanager_secret                                    | AWS Secrets Manager Secret                                         |
| aws_securityhub_action_target                                | AWS Security Hub Action Target                                     |
| aws_securityhub_finding                                      | AWS Security Hub Finding                                           |
| aws_securityhub_finding_aggregator                           | AWS Security Hub Finding Aggregator                                |
| aws_securityhub_hub                                          | AWS Security Hub                                                   |
| aws_securityhub_insight                                      | AWS Securityhub Insight                                            |
| aws_securityhub_member                                       | AWS Securityhub Member                                             |
| aws_securityhub_product                                      | AWS Securityhub Product                                            |
| aws_securityhub_standards_control                            | AWS Security Hub Standards Control                                 |
| aws_securityhub_standards_subscription                       | AWS Security Hub Standards Subscription                            |
| aws_securitylake_data_lake                                   | AWS Security Lake Data Lake                                        |
| aws_securitylake_subscriber                                  | AWS Security Lake Subscriber                                       |
| aws_serverlessapplicationrepository_application              | AWS Serverless Application Repository Application                  |
| aws_service_discovery_instance                               | AWS Service Discovery Instance                                     |
| aws_service_discovery_namespace                              | AWS Service Discovery Namespace                                    |
| aws_service_discovery_service                                | AWS Service Discovery Service                                      |
| aws_servicecatalog_portfolio                                 | AWS Service Catalog Portfolio                                      |
| aws_servicecatalog_product                                   | AWS Service Catalog Product                                        |
| aws_servicecatalog_provisioned_product                       | AWS Service Catalog Provisioned Product                            |
| aws_servicequotas_default_service_quota                      | AWS Service Quotas Default Service Quota                           |
| aws_servicequotas_service                                    | AWS Service Quotas Service                                         |
| aws_servicequotas_service_quota                              | AWS Service Quotas Service Quota                                   |
| aws_servicequotas_service_quota_change_request               | AWS Service Quotas Service Quota Change Request                    |
| aws_ses_domain_identity                                      | AWS SES Domain Identity                                            |
| aws_ses_email_identity                                       | AWS SES Email Identity                                             |
| aws_sfn_state_machine                                        | AWS Step Functions State Machine                                   |
| aws_sfn_state_machine_execution                              | AWS Step Functions State Machine Execution                         |
| aws_sfn_state_machine_execution_history                      | AWS Step Functions State Machine Execution History                 |
| aws_simspaceweaver_simulation                                | AWS SimSpace Weaver Simulation                                     |
| aws_sns_subscription                                         | AWS SNS Subscription                                               |
| aws_sns_topic                                                | AWS SNS Topic                                                      |
| aws_sns_topic_subscription                                   | AWS SNS Topic Subscription                                         |
| aws_sqs_queue                                                | AWS SQS Queue                                                      |
| aws_ssm_association                                          | AWS SSM Association                                                |
| aws_ssm_document                                             | AWS SSM Document                                                   |
| aws_ssm_document_permission                                  | AWS SSM Document Permission                                        |
| aws_ssm_inventory                                            | AWS SSM Inventory                                                  |
| aws_ssm_inventory_entry                                      | AWS SSM Inventory Entry                                            |
| aws_ssm_maintenance_window                                   | AWS SSM Maintenance Window                                         |
| aws_ssm_managed_instance                                     | AWS SSM Managed Instance                                           |
| aws_ssm_managed_instance_compliance                          | AWS SSM Managed Instance Compliance                                |
| aws_ssm_managed_instance_patch_state                         | AWS SSM Managed Instance Patch State                               |
| aws_ssm_parameter                                            | AWS SSM Parameter                                                  |
| aws_ssm_patch_baseline                                       | AWS SSM Patch Baseline                                             |
| aws_ssmincidents_response_plan                               | AWS SSMIncidents Response Plan                                     |
| aws_ssoadmin_account_assignment                              | AWS SSO Account Assignment                                         |
| aws_ssoadmin_instance                                        | AWS SSO Instance                                                   |
| aws_ssoadmin_managed_policy_attachment                       | AWS SSO Managed Policy Attachment                                  |
| aws_ssoadmin_permission_set                                  | AWS SSO Permission Set                                             |
| aws_sts_caller_identity                                      | AWS STS Caller Identity                                            |
| aws_tagging_resource                                         | AWS Tagging Resource                                               |
| aws_transfer_server                                          | AWS Transfer Server                                                |
| aws_transfer_user                                            | AWS Transfer User                                                  |
| aws_trusted_advisor_check_summary                            | AWS Trusted Advisor Check Summary                                  |
| aws_vpc                                                      | AWS VPC                                                            |
| aws_vpc_customer_gateway                                     | AWS VPC Customer Gateway                                           |
| aws_vpc_dhcp_options                                         | AWS VPC DHCP Options                                               |
| aws_vpc_egress_only_internet_gateway                         | AWS VPC Egress Only Internet Gateway                               |
| aws_vpc_eip                                                  | AWS VPC Elastic IP                                                 |
| aws_vpc_eip_address_transfer                                 | AWS VPC Elastic IP Address Transfer                                |
| aws_vpc_endpoint                                             | AWS VPC Endpoint                                                   |
| aws_vpc_endpoint_service                                     | AWS VPC Endpoint Service                                           |
| aws_vpc_flow_log                                             | AWS VPC Flowlog                                                    |
| aws_vpc_flow_log_event                                       | AWS VPC Flow Log events from CloudWatch Logs                       |
| aws_vpc_internet_gateway                                     | AWS VPC Internet Gateway                                           |
| aws_vpc_nat_gateway                                          | AWS VPC Network Address Translation Gateway                        |
| aws_vpc_nat_gateway_metric_bytes_out_to_destination          | AWS VPC Nat Gateway Cloudwatch Metrics - BytesOutToDestination     |
| aws_vpc_network_acl                                          | AWS VPC Network ACL                                                |
| aws_vpc_peering_connection                                   | AWS VPC Peering Connection                                         |
| aws_vpc_route                                                | AWS VPC Route                                                      |
| aws_vpc_route_table                                          | AWS VPC Route table                                                |
| aws_vpc_security_group                                       | AWS VPC Security Group                                             |
| aws_vpc_security_group_rule                                  | AWS VPC Security Group Rule                                        |
| aws_vpc_subnet                                               | AWS VPC Subnet                                                     |
| aws_vpc_verified_access_endpoint                             | AWS VPC verified access Endpoint                                   |
| aws_vpc_verified_access_group                                | AWS VPC Verified Access Group                                      |
| aws_vpc_verified_access_instance                             | AWS VPC Verified Access Instance                                   |
| aws_vpc_verified_access_trust_provider                       | AWS VPC Verified Access Trust Provider                             |
| aws_vpc_vpn_connection                                       | AWS VPC VPN Connection                                             |
| aws_vpc_vpn_gateway                                          | AWS VPC VPN Gateway                                                |
| aws_waf_rate_based_rule                                      | AWS WAF Rate Based Rule                                            |
| aws_waf_rule                                                 | AWS WAF Rule                                                       |
| aws_waf_rule_group                                           | AWS WAF Rule Group                                                 |
| aws_waf_web_acl                                              | AWS WAF Web ACL                                                    |
| aws_wafregional_rule                                         | AWS WAF Regional Rule                                              |
| aws_wafregional_rule_group                                   | AWS WAF Regional Rule Group                                        |
| aws_wafregional_web_acl                                      | AWS WAF Regional Web ACL                                           |
| aws_wafv2_ip_set                                             | AWS WAFv2 IP Set                                                   |
| aws_wafv2_regex_pattern_set                                  | AWS WAFv2 Regex Pattern Set                                        |
| aws_wafv2_rule_group                                         | AWS WAFv2 Rule Group                                               |
| aws_wafv2_web_acl                                            | AWS WAFv2 Web ACL                                                  |
| aws_wellarchitected_answer                                   | AWS Well-Architected Answer                                        |
| aws_wellarchitected_check_detail                             | AWS Well-Architected Check Detail                                  |
| aws_wellarchitected_check_summary                            | AWS Well-Architected Check Summary                                 |
| aws_wellarchitected_consolidated_report                      | AWS Well-Architected Consolidated Report                           |
| aws_wellarchitected_lens                                     | AWS Well-Architected Lens                                          |
| aws_wellarchitected_lens_review                              | AWS Well-Architected Lens Review                                   |
| aws_wellarchitected_lens_review_improvement                  | AWS Well-Architected Lens Review Improvement                       |
| aws_wellarchitected_lens_review_report                       | AWS Well-Architected Lens Review Report                            |
| aws_wellarchitected_lens_share                               | AWS Well-Architected Lens Share                                    |
| aws_wellarchitected_milestone                                | AWS Well-Architected Milestone                                     |
| aws_wellarchitected_notification                             | AWS Well-Architected Notification                                  |
| aws_wellarchitected_share_invitation                         | AWS Well-Architected Share Invitation                              |
| aws_wellarchitected_workload                                 | AWS Well-Architected Workload                                      |
| aws_wellarchitected_workload_share                           | AWS Well-Architected Workload Share                                |
| aws_workspaces_directory                                     | AWS Workspaces Directory                                           |
| aws_workspaces_workspace                                     | AWS Workspaces                                                     |
+--------------------------------------------------------------+--------------------------------------------------------------------+
 ==> steampipe
+-----------------------------------+-----------------------------------+
| table                             | description                       |
+-----------------------------------+-----------------------------------+
| steampipe_registry_plugin         | Steampipe Registry Plugins        |
| steampipe_registry_plugin_version | Steampipe Registry Plugin Version |
+-----------------------------------+-----------------------------------+

To get information about the columns in a table, run .inspect {connection}.{table}
```

table gcp
```
 ==> gcp
+---------------------------------------------------------+--------------------------------------------------------------+
| table                                                   | description                                                  |
+---------------------------------------------------------+--------------------------------------------------------------+
| gcp_alloydb_cluster                                     | GCP AlloyDB Cluster                                          |
| gcp_alloydb_instance                                    | GCP AlloyDB Instance                                         |
| gcp_apikeys_key                                         | GCP API Keys Key                                             |
| gcp_app_engine_application                              | GCP App Engine Application                                   |
| gcp_artifact_registry_repository                        | GCP Artifact Registry Repository                             |
| gcp_audit_policy                                        | GCP Audit Policy                                             |
| gcp_bigquery_dataset                                    | GCP BigQuery Dataset                                         |
| gcp_bigquery_job                                        | GCP BigQuery Job                                             |
| gcp_bigquery_table                                      | GCP Bigquery Table                                           |
| gcp_bigtable_instance                                   | GCP Bigtable Instance                                        |
| gcp_billing_account                                     | GCP Billing Account                                          |
| gcp_billing_budget                                      | GCP Billing Budget                                           |
| gcp_cloud_asset                                         | GCP Cloud Asset                                              |
| gcp_cloud_identity_group                                | GCP Cloud Identity Group                                     |
| gcp_cloud_identity_group_membership                     | GCP Cloud Identity Group Membership                          |
| gcp_cloud_run_service                                   | GCP Cloud Run Service                                        |
| gcp_cloudfunctions_function                             | GCP Cloud Function                                           |
| gcp_compute_address                                     | GCP Compute Address                                          |
| gcp_compute_autoscaler                                  | GCP Compute Autoscaler                                       |
| gcp_compute_backend_bucket                              | GCP Compute Backend Bucket                                   |
| gcp_compute_backend_service                             | GCP Compute Backend Service                                  |
| gcp_compute_disk                                        | GCP Compute Disk                                             |
| gcp_compute_disk_metric_read_ops                        | GCP Compute Disk Metrics - Read Ops                          |
| gcp_compute_disk_metric_read_ops_daily                  | GCP Compute Disk Metrics - Read Ops (Daily)                  |
| gcp_compute_disk_metric_read_ops_hourly                 | GCP Compute Disk Metrics - Read Ops (Hourly)                 |
| gcp_compute_disk_metric_write_ops                       | GCP Compute Disk Metrics - Write Ops                         |
| gcp_compute_disk_metric_write_ops_daily                 | GCP Compute Disk Metrics - Write Ops (Daily)                 |
| gcp_compute_disk_metric_write_ops_hourly                | GCP Compute Disk Metrics - Write Ops (Hourly)                |
| gcp_compute_firewall                                    | GCP Compute Firewall                                         |
| gcp_compute_forwarding_rule                             | GCP Compute Forwarding Rule                                  |
| gcp_compute_global_address                              | GCP Compute Global Address                                   |
| gcp_compute_global_forwarding_rule                      | GCP Compute Global Forwarding Rule                           |
| gcp_compute_ha_vpn_gateway                              | GCP Compute VPN Gateway                                      |
| gcp_compute_image                                       | GCP Compute Image                                            |
| gcp_compute_instance                                    | GCP Compute Instance                                         |
| gcp_compute_instance_group                              | GCP Compute Instance Group                                   |
| gcp_compute_instance_metric_cpu_utilization             | GCP Compute Instance Metrics - CPU Utilization               |
| gcp_compute_instance_metric_cpu_utilization_daily       | GCP Compute Instance Metrics - CPU Utilization (Daily)       |
| gcp_compute_instance_metric_cpu_utilization_hourly      | GCP Compute Instance Metrics - CPU Utilization (Hourly)      |
| gcp_compute_instance_template                           | GCP Compute Instance Template                                |
| gcp_compute_machine_image                               | GCP Compute Machine Image                                    |
| gcp_compute_machine_type                                | GCP Compute Machine Type                                     |
| gcp_compute_network                                     | GCP Compute Network                                          |
| gcp_compute_node_group                                  | GCP Compute Node Group                                       |
| gcp_compute_node_template                               | GCP Compute Node Template                                    |
| gcp_compute_project_metadata                            | GCP Compute Project Metadata                                 |
| gcp_compute_region                                      | GCP Compute Region                                           |
| gcp_compute_resource_policy                             | GCP Compute Resource Policy                                  |
| gcp_compute_router                                      | GCP Compute Router                                           |
| gcp_compute_snapshot                                    | GCP Compute Snapshot                                         |
| gcp_compute_ssl_policy                                  | GCP Compute SSL Policy                                       |
| gcp_compute_subnetwork                                  | GCP Compute Subnetwork                                       |
| gcp_compute_target_https_proxy                          | GCP Compute Target Https Proxy                               |
| gcp_compute_target_pool                                 | GCP Compute Target Pool                                      |
| gcp_compute_target_ssl_proxy                            | GCP Compute Target SSL Proxy                                 |
| gcp_compute_target_vpn_gateway                          | GCP Compute Target VPN Gateway                               |
| gcp_compute_url_map                                     | GCP Compute URL Map                                          |
| gcp_compute_vpn_tunnel                                  | GCP Compute VPN Tunnel                                       |
| gcp_compute_zone                                        | GCP Compute Zone                                             |
| gcp_dataproc_cluster                                    | GCP Dataproc Cluster                                         |
| gcp_dns_managed_zone                                    | GCP DNS Managed Zone                                         |
| gcp_dns_policy                                          | GCP DNS Policy                                               |
| gcp_dns_record_set                                      | GCP DNS Record Set                                           |
| gcp_iam_policy                                          | GCP IAM Policy                                               |
| gcp_iam_role                                            | GCP IAM Role                                                 |
| gcp_kms_key                                             | GCP KMS Key                                                  |
| gcp_kms_key_ring                                        | GCP KMS Key Ring                                             |
| gcp_kms_key_version                                     | GCP KMS Key Version                                          |
| gcp_kubernetes_cluster                                  | GCP Kubernetes Cluster                                       |
| gcp_kubernetes_node_pool                                | GCP Kubernetes Node Pool                                     |
| gcp_logging_bucket                                      | GCP Logging Bucket                                           |
| gcp_logging_exclusion                                   | GCP Logging Exclusion                                        |
| gcp_logging_log_entry                                   | GCP Logging Log Entry                                        |
| gcp_logging_metric                                      | GCP Logging Metric                                           |
| gcp_logging_sink                                        | GCP Logging Sink                                             |
| gcp_monitoring_alert_policy                             | GCP Monitoring Alert Policy                                  |
| gcp_monitoring_group                                    | GCP Monitoring Group                                         |
| gcp_monitoring_notification_channel                     | GCP Monitoring Notification Channel                          |
| gcp_organization                                        | GCP Organization                                             |
| gcp_project                                             | GCP Project                                                  |
| gcp_project_organization_policy                         | GCP Project Organization Policy                              |
| gcp_project_service                                     | GCP Project Service                                          |
| gcp_pubsub_snapshot                                     | GCP Pub/Sub Snapshot                                         |
| gcp_pubsub_subscription                                 | GCP Pub/Sub Subscription                                     |
| gcp_pubsub_topic                                        | GCP Pub/Sub Topic                                            |
| gcp_redis_instance                                      | GCP Redis Instance                                           |
| gcp_secret_manager_secret                               | GCP Secret Manager Secret                                    |
| gcp_service_account                                     | GCP Service Account                                          |
| gcp_service_account_key                                 | GCP Service Account Key                                      |
| gcp_sql_backup                                          | GCP SQL Backup                                               |
| gcp_sql_database                                        | GCP SQL Database                                             |
| gcp_sql_database_instance                               | GCP SQL Database Instance                                    |
| gcp_sql_database_instance_metric_connections            | GCP SQL Database Instance Metrics Connections                |
| gcp_sql_database_instance_metric_connections_daily      | GCP SQL Database Instance Metrics - Connections (Daily)      |
| gcp_sql_database_instance_metric_connections_hourly     | GCP SQL Database Instance Metrics - Connections (Hourly)     |
| gcp_sql_database_instance_metric_cpu_utilization        | GCP SQL Database Instance Metrics - CPU Utilization          |
| gcp_sql_database_instance_metric_cpu_utilization_daily  | GCP SQL Database Instance Metrics - CPU Utilization (Daily)  |
| gcp_sql_database_instance_metric_cpu_utilization_hourly | GCP SQL Database Instance Metrics - CPU Utilization (Hourly) |
| gcp_storage_bucket                                      | GCP Storage Bucket                                           |
| gcp_storage_object                                      | GCP Storage Object                                           |
| gcp_tag_binding                                         | GCP Tag Binding                                              |
| gcp_vertex_ai_endpoint                                  | GCP Vertex AI Endpoint                                       |
| gcp_vertex_ai_model                                     | GCP Vertex AI Model                                          |
+---------------------------------------------------------+--------------------------------------------------------------+
 ==> steampipe
+-----------------------------------+-----------------------------------+
| table                             | description                       |
+-----------------------------------+-----------------------------------+
| steampipe_registry_plugin         | Steampipe Registry Plugins        |
| steampipe_registry_plugin_version | Steampipe Registry Plugin Version |
+-----------------------------------+-----------------------------------+

To get information about the columns in a table, run .inspect {connection}.{table}
```

final table
```
| **GCP Service**                        | **AWS Service**                       | **AWS Equivalent**                        | **Description**                                                                 |
|---------------------------------------|--------------------------------------|-------------------------------------------|---------------------------------------------------------------------------------|
| gcp_alloydb_cluster                   | aws_rds_alloydb_cluster               | AWS RDS/Aurora                            | Managed database services (AlloyDB is similar to Amazon Aurora)                  |
| gcp_alloydb_instance                  | aws_rds_alloydb_instance              | AWS RDS/Aurora Instances                  | Database instances (AlloyDB instances are similar to RDS instances)              |
| gcp_apikeys_key                       | aws_apigateway_api_keys               | AWS API Gateway API Keys                  | API key management                                                                 |
| gcp_app_engine_application            | aws_elastic_beanstalk_application     | AWS Elastic Beanstalk                     | Platform as a Service (PaaS)                                                        |
| gcp_artifact_registry_repository      | aws_codeartifact_repository           | AWS CodeArtifact                          | Artifact repository                                                                  |
| gcp_audit_policy                      | aws_cloudtrail_audit_policy           | AWS CloudTrail                            | Audit logging and policy management                                                |
| gcp_bigquery_dataset                  | aws_redshift_dataset                  | AWS Redshift, AWS Athena                  | Data warehousing and analytics                                                       |
| gcp_bigquery_job                      | aws_glue_job                          | AWS Glue Jobs, AWS Redshift Queries       | Data processing jobs                                                                |
| gcp_bigquery_table                    | aws_redshift_table                    | AWS Glue Data Catalog, AWS Redshift Tables| Data storage and cataloging                                                          |
| gcp_bigtable_instance                 | aws_dynamodb_instance                 | AWS DynamoDB                              | NoSQL database                                                                      |
| gcp_billing_account                   | aws_billing_account                   | AWS Billing and Cost Management           | Cost management and billing                                                          |
| gcp_billing_budget                    | aws_budgets                           | AWS Budgets                               | Budget management and alerts                                                         |
| gcp_cloud_asset                       | aws_config_resource                  | AWS Config                                | Resource configuration tracking                                                      |
| gcp_cloud_identity_group              | aws_iam_groups                        | AWS IAM Groups                            | Identity and access management                                                        |
| gcp_cloud_identity_group_membership   | aws_iam_roles_policies                | AWS IAM Roles and Policies                | Identity and access management                                                        |
| gcp_cloud_run_service                 | aws_fargate_service                   | AWS Fargate, AWS Lambda                   | Serverless compute services                                                          |
| gcp_cloudfunctions_function           | aws_lambda_function                  | AWS Lambda                                | Serverless compute functions                                                          |
| gcp_compute_address                   | aws_elastic_ip                        | AWS Elastic IPs                           | Static IP management                                                                 |
| gcp_compute_autoscaler                | aws_autoscaling                       | AWS Auto Scaling                          | Auto-scaling for compute resources                                                     |
| gcp_compute_backend_bucket            | aws_s3_bucket                         | AWS S3                                    | Object storage                                                                        |
| gcp_compute_backend_service           | aws_elastic_load_balancer             | AWS ELB, AWS Application Load Balancer    | Load balancing                                                                       |
| gcp_compute_disk                      | aws_ebs_volume                        | AWS EBS                                   | Block storage                                                                        |
| gcp_compute_firewall                  | aws_security_group                    | AWS Security Groups                       | Network security and access control                                                    |
| gcp_compute_forwarding_rule           | aws_route53_forwarding_rule           | AWS Route 53                              | DNS and routing                                                                       |
| gcp_compute_global_address            | aws_global_accelerator                | AWS Global Accelerator                    | Global network routing                                                               |
| gcp_compute_global_forwarding_rule    | aws_global_accelerator                | AWS Global Accelerator                    | Global load balancing                                                                 |
| gcp_compute_ha_vpn_gateway            | aws_vpn_gateway                       | AWS VPN Gateway                           | VPN services                                                                          |
| gcp_compute_image                     | aws_ami                               | AWS AMI                                   | Machine images                                                                       |
| gcp_compute_instance                  | aws_ec2_instance                      | AWS EC2                                   | Virtual servers                                                                      |
| gcp_compute_instance_group            | aws_ec2_auto_scaling_group            | AWS EC2 Auto Scaling Groups               | Managed instance groups                                                               |
| gcp_compute_instance_metric_cpu_utilization | aws_cloudwatch_metrics_cpu_utilization | AWS CloudWatch Metrics                    | Resource monitoring and metrics                                                       |
| gcp_compute_instance_template         | aws_ec2_launch_template               | AWS EC2 Launch Templates                  | Instance templates                                                                   |
| gcp_compute_machine_image             | aws_ami                               | AWS AMI                                   | Machine images                                                                       |
| gcp_compute_machine_type              | aws_ec2_instance_type                 | AWS EC2 Instance Types                    | Instance types                                                                       |
| gcp_compute_network                   | aws_vpc                               | AWS VPC                                   | Virtual networking                                                                    |
| gcp_compute_node_group                | aws_ec2_auto_scaling_group            | AWS EC2 Auto Scaling Groups               | Managed instance groups                                                               |
| gcp_compute_node_template             | aws_ec2_launch_template               | AWS EC2 Launch Templates                  | Instance templates                                                                   |
| gcp_compute_project_metadata          | aws_resource_tags                     | AWS Resource Tags                         | Metadata and tagging                                                                  |
| gcp_compute_region                    | aws_region                            | AWS Regions                               | Geographic regions                                                                    |
| gcp_compute_resource_policy           | aws_iam_policy                        | AWS IAM Policies                          | Resource policies and management                                                      |
| gcp_compute_router                    | aws_transit_gateway                   | AWS Transit Gateway                       | Network routing and management                                                        |
| gcp_compute_snapshot                  | aws_ebs_snapshot                      | AWS EBS Snapshots                          | Volume snapshots                                                                       |
| gcp_compute_ssl_policy                | aws_acm_certificate                   | AWS ACM                                   | SSL/TLS certificate management                                                        |
| gcp_compute_subnetwork                | aws_vpc_subnet                        | AWS VPC Subnets                           | Subnet management within VPC                                                           |
| gcp_compute_target_https_proxy        | aws_application_load_balancer         | AWS Application Load Balancer (ALB)      | HTTPS load balancing                                                                  |
| gcp_compute_target_pool               | aws_elastic_load_balancer             | AWS ELB                                   | Load balancing                                                                       |
| gcp_compute_target_ssl_proxy          | aws_acm_certificate                   | AWS ACM                                   | SSL/TLS certificate management                                                        |
| gcp_compute_target_vpn_gateway        | aws_vpn_gateway                       | AWS VPN Gateway                           | VPN services                                                                          |
| gcp_compute_url_map                   | aws_application_load_balancer_rules   | AWS ALB Rules                             | URL routing and management                                                           |
| gcp_compute_vpn_tunnel                | aws_vpn_connection                    | AWS VPN Connections                       | VPN tunnels                                                                          |
| gcp_compute_zone                      | aws_availability_zone                 | AWS Availability Zones                    | Geographic availability zones                                                          |
| gcp_dataproc_cluster                  | aws_emr_cluster                       | AWS EMR                                   | Big data processing                                                                    |
| gcp_dns_managed_zone                  | aws_route53_hosted_zone               | AWS Route 53 Hosted Zones                 | DNS management                                                                        |
| gcp_dns_policy                        | aws_route53_dns_policy                | AWS Route 53 DNS Policies                 | DNS policies                                                                         |
| gcp_dns_record_set                    | aws_route53_record                    | AWS Route 53 Records                      | DNS records                                                                          |
| gcp_iam_policy                        | aws_iam_policy                        | AWS IAM Policies                          | IAM policies                                                                         |
| gcp_iam_role                          | aws_iam_role                          | AWS IAM Roles                             | IAM roles                                                                            |
| gcp_kms_key                           | aws_kms_key                           | AWS KMS                                   | Key management                                                                        |
| gcp_kms_key_ring                      | aws_kms_key_ring                      | AWS KMS Key Rings                         | Key management                                                                        |
| gcp_kms_key_version                   | aws_kms_key_version                   | AWS KMS Key Versions                      | Key versions                                                                          |
| gcp_kubernetes_cluster                | aws_eks_cluster                       | AWS EKS                                   | Managed Kubernetes service                                                             |
| gcp_kubernetes_node_pool              | aws_eks_node_group                    | AWS EKS Node Groups                       | Kubernetes node pools                                                                 |
| gcp_logging_bucket                    | aws_s3_bucket                         | AWS S3                                    | Logging storage                                                                       |
| gcp_logging_exclusion                 | aws_cloudwatch_logs_exclusion         | AWS CloudWatch Logs Insights Exclusion    | Log exclusion                                                                        |
| gcp_logging_log_entry                 | aws_cloudwatch_logs                   | AWS CloudWatch Logs                       | Log entries                                                                           |
| gcp_logging_metric                    | aws_cloudwatch_metric                | AWS CloudWatch Metrics                    | Metric data                                                                          |
| gcp_logging_sink                      | aws_cloudwatch_log_group              | AWS CloudWatch Log Groups                 | Log aggregation and storage                                                           |
| gcp_monitoring_alert_policy           | aws_cloudwatch_alarm                  | AWS CloudWatch Alarms                     | Alert policies                                                                        |
| gcp_monitoring_group                  | aws_cloudwatch_dashboard              | AWS CloudWatch Dashboard                  | Monitoring groups                                                                     |
| gcp_monitoring_notification_channel   | aws_sns_topic                         | AWS SNS Notifications                     | Alert notifications                                                                    |
| gcp_organization                      | aws_organizations                     | AWS Organizations                         | Organization management                                                               |
| gcp_project                           | aws_account                           | AWS Accounts                              | GCP projects and AWS accounts                                                         |
| gcp_project_organization_policy      | aws_organizations_policy             | AWS Organizations Policies                | Organizational policies                                                               |
| gcp_project_service                   | aws_service                           | AWS Services                              | Project service management                                                            |
| gcp_pubsub_snapshot                   | aws_sqs                               | AWS SQS                                   | Message queues and snapshots                                                          |
| gcp_pubsub_subscription               | aws_sqs_subscription                  | AWS SQS Subscriptions                     | Queue subscriptions                                                                   |
| gcp_pubsub_topic                      | aws_sns_topic                         | AWS SNS Topics

                            | Pub/Sub messaging topics                                                              |
| gcp_redis_instance                    | aws_elasticache_redis                 | AWS ElastiCache Redis                     | In-memory data store                                                                  |
| gcp_secret_manager_secret             | aws_secrets_manager_secret            | AWS Secrets Manager                       | Secret management                                                                      |
| gcp_service_account                   | aws_iam_service_account               | AWS IAM Service Accounts                  | Service accounts                                                                       |
| gcp_service_account_key               | aws_iam_service_account_key           | AWS IAM Service Account Keys              | Service account keys                                                                  |
| gcp_sql_backup                        | aws_rds_backup                        | AWS RDS Backups                           | Database backups                                                                      |
| gcp_sql_database                      | aws_rds_database                      | AWS RDS Databases                         | Managed SQL databases                                                                  |
| gcp_sql_database_instance             | aws_rds_instance                      | AWS RDS Instances                         | Database instances                                                                     |
| gcp_sql_database_instance_metric_connections | aws_rds_metric_connections          | AWS RDS CloudWatch Metrics                | Database connections metrics                                                           |
| gcp_sql_database_instance_metric_cpu_utilization | aws_rds_metric_cpu_utilization      | AWS RDS CloudWatch Metrics                | Database CPU utilization metrics                                                       |
| gcp_storage_bucket                    | aws_s3_bucket                         | AWS S3                                    | Object storage                                                                        |
| gcp_storage_object                    | aws_s3_object                         | AWS S3 Objects                            | Stored objects                                                                         |
| gcp_tag_binding                       | aws_resource_tag                      | AWS Resource Tags                         | Tag management                                                                         |
| gcp_vertex_ai_endpoint                | aws_sagemaker_endpoint                | AWS SageMaker Endpoints                   | AI and ML model endpoints                                                              |
| gcp_vertex_ai_model                   | aws_sagemaker_model                   | AWS SageMaker Models                      | AI and ML models                                                                       |

```
