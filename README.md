# CloudWatch Export
Export a CloudWatch log groups to S3 on a recurring schedule using Lambda and CloudWatch Events. This module requires `curl` be available on the machine running terraform so that it can download the lambda zip.

## Example

    module "cloudwatch-exporter" {
      source           = "gadgetry-io/cloudwatch-logs-exporter/aws"
      version          = "0.0.1"
      
      name             = "vpc-flow-logs"
      log_group        = "/prd/vpc_flow_logs"
      s3_bucket        = "my-s3-bucket"
      s3_prefix        = "cloudwatch/prd/vpc_flow_logs"
    }
