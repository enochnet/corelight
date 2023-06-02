3 Lambda functions have been created.


- apigw

- s3lamda

- sqslamda


 Get and Put methods have also been implemented with the API


As the flow directs, any get request triggers the “apigw” Lambda and it logs the request on cloudwatch log group(/aws/lamda/apigw) and send the message to sqs queue(corelight-enoch), the second Lambda (sqslamda) is being triggered by this event on the sqs queue and then processes the message and logs the request on teh cloudwatch log group(/aws/lamda/sqslamda) and then  creates the “message.json” object in the s3 bucket(corelight-enoch), this request is also logged to the cloudwatch log group(/aws/lamda/s3lamda)


The iam role used for deploying the Lambda is enoch-lamda and it has the s3, sqs and cloudwatch policies attached.
