# tf-aws-alarms

Terraform module to Set up CloudWatch alarms to notify you when critical changes happen in your AWS account.

## AWS Resources

- AWS SNS Topic - Destination for CloudWatch Alarms/Events (create)
- CloudWatch Filters/Metric alarms (create)
- CloudTrail Group to Monitor (use existing)

## Variables

### Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| alarm_namespace | The namespace in which all alarms are set up. | string |  `CISBenchmark` | yes |
| cloudtrail_log_group_name | The name of the CloudWatch Logs group to which CloudTrail events are delivered | string | `string` | yes |
| sns_topic_name | Name of the SNS topic to subscribe to. | string | `CISAlarm` | yes |

## Usage

To use this module:

```
module "aws_alarms" {
    source                      = "git@github.com:cjbischoff/tf-aws-alarms.git?ref=<VERSION>"
    alarm_namespace             = "Alarm_Name"
    cloudtrail_log_group_name   = "Existing CloudTrail Name"
    sns_topic_name              = "Topic_Name"
    }
```
