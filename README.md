# tool-cf-StartStop-SagemakerMLFlowTrackingServer



## Name
tool-cf-StartStop-SagemakerMLFlowTrackingServer

## Description
This Cloudformation template deployes automation to start at stop Amazon Sagemaker Mlflow Tracking Server.
As currently there is no built in scheduler in Sagemaker or native support as a target API for EventBridge Scheduler this solution deploys a Lambda function that receives event['action'] in the invokation payload action=='start' or action=='stop'.
The tracking_server_name is provided as a parameter in the cf template and made available to Lambda via os variable.

2 Eventbridge schedules are created , 1 to invoke the function with a 'start' parameter and another with a 'stop' parameter.

The cron expressions to this schedules are passed as parameters in the cf template as well and have defaults for Mon-Fri 07h00 - 19h00 in Europe/Berlin timezone.


## Authors and acknowledgment
bquintas@
