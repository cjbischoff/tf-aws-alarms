# tf-aws-alarms

Terraform module to Set up CloudWatch alarms to notify you when critical changes happen in your AWS account.

## AWS Resources

- AWS SNS Topic - Destination for CloudWatch Alarms/Events
- CloudWatch Filters/Metric alarms
- CLoudTrail Group to Monitor

## Variables

### Inputs

- `alarm_namespace` :  The namespace in which all alarms are set up. (default = "CISBenchmark")
- `cloudtrail_log_group_name` : The name of the CloudWatch Logs group to which CloudTrail events are delivered.
- `sns_topic_name` : The name of the SNS Topic which will be notified when any alarm is performed.(default = "CISAlarm")

### Outputs

- `alarm_topic_arn` : The ARN of the SNS topic to which CloudWatch Alarms will be sent.

## Usage

To use this module:

```
module "aws_alarms" {
    source                    = "git@github.com:cjbischoff/tf-aws-alarms.git?ref=<VERSION>"
    alarm_namespace           = "Alarm_Name"
    cloudtrail_log_group_name = "Existing CloudTrail Name"
    sns_topic_name            = "Topic_Name"
}
```
