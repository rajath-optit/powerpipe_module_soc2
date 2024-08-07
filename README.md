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

```
