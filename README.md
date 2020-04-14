# Ebextension - AWS Elastic Beanstalk - EFS - PHP
# Deploying the AWS Elastic Beanstalk in wordpress with EFS automount
- [Introduction](#Introduction)
- [Installation and configuration](#Installation-and-configuration)
- [Flow](#Flow)

# Introduction
In this post, we will be using Ebextension to mount the EFS in Elastic beanstalk.

# Installation and configuration
Clone the project locally to your linux machine.

Copy the ebxtenstion as .ebxtenstion in your core code and upload a same in your AWS Elastic Beanstalk.

```
cp -r ebxtenstion <path_to_your_application>/.ebxtenstion
```

Add the below Environment properties in you Elastic Beanstalk.

| key | value |
| ------------- | ------------- |
| EFS_NAME              | <efs_dns_name>        |

# Flow

1. Install nfs-utils and jq for the mounting purpose.
2. Simple bash script to mount the efs to ***/mnt/efs/uploads***
3. Remove the /var/app/ondeck/wp-content/uploads ***/var/app/ondeck/wp-content/uploads*** directory.
4. Link the ***/var/app/ondeck/wp-content/uploads*** to ***/mnt/efs/uploads***


