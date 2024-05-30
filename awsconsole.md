aws console . 


fields @timestamp, @message
| filter @message like /error/
| sort @timestamp desc
| limit 20

