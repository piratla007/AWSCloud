
# Kinesis Data Firehose
Cloud Formation Template for creating Kinesis Firehose for storing the Stream

**Prerequisites**
- Download the [TransformSourceRecordswithAWSLambda.zip](https://github.com/piratla007/CF-Kinesis-Data-Firehose/blob/master/TransformSourceRecordswithAWSLambda.zip "TransformSourceRecordswithAWSLambda.zip") from this repository to local machine
- Create a S3 Bucket by using either AWS Console or following command, make sure the bucket name is unique.  
`aws s3 mb s3://<bucket-name>`
- Upload the previously dowloaded file to s3 bucket using console or using following command.  
`aws s3 cp <absolutepath>/TransformSourceRecordswithAWSLambda.zip s3://<bucket-name>`


#### Executing the Cloud Formation Template 
- Download [KinesisFirehoseDeliveryStream.json](https://github.com/piratla007/CF-Kinesis-Data-Firehose/blob/master/KinesisFirehoseDeliveryStream.json "KinesisFirehoseDeliveryStream.json") from repository
- Navigate to [Cloud Formation](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filter=active "Cloud Formation") section in AWS Console
- Create new stack using the downloaded [KinesisFirehoseDeliveryStream.json](https://github.com/piratla007/CF-Kinesis-Data-Firehose/blob/master/KinesisFirehoseDeliveryStream.json "KinesisFirehoseDeliveryStream.json") file
- In Parameters section, for **BucketForLambdaCode** Provide bucket name which has the Lambda function code and for **LambdaCode** provide the zipped file name.

**Resources that will be created**
- One S3 bucket to get all streams stored
- Role for Kinesis
- Role for Lambda function execution
- Lambda function for Data Transformation
- Kinesis Fire hose stream
