# CloudWatch Alarms - Metrics by Namespaces

[AWS Documentation - CloudWatch Metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/viewing_metrics_with_cloudwatch.html)


## How to use

> To view available metrics by namespace, dimension, or metric using the AWS CLI
- If you want to get the list of metrics available for a AWS service namespace, you could do:
    - `aws cloudwatch list-metrics --namespace AWS/EC2`

> To list all the available metrics for a specified resource
- The following example specifies the AWS/EC2 namespace and the InstanceId dimension to view the results for the specified instance only
    - `aws cloudwatch list-metrics --namespace AWS/EC2 --dimensions Name=InstanceId,Value=i-1234567890abcdef0`

> To list a metric for all resources
- The following example specifies the AWS/EC2 namespace and a metric name to view the results for the specified metric only.
    - `aws cloudwatch list-metrics --namespace AWS/EC2 --metric-name CPUUtilization`
