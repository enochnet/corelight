I created 3 lamda functions

apigw
s3lamda
sqslamda


I created an api called lamda and created get and put method on the api

As the flow directs, any get request on the api triiggers the “apigw” lamda and
it logs the request on cloudwatch log group(/aws/lamda/apigw)
and send the message to sqs queue(corelight-enoch), 
the second lamda(sqslamda) is being triggered by this event on the sqs queue
it processes the message and logs the request on teh cloudwatch log group(/aws/lamda/sqslamda)
it proceeds to create the “message.json” object in the s3 bucket(corelight-enoch),
this request is also logged to the cloudwatch log group(/aws/lamda/s3lamda)

The iam role used for deploying the lamda is enoch-lamda and it has the s3, sqs and cloudwatch policies attached.
