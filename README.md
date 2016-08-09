ELK Stack with AWS ES
===========================

ELK stands for Elasticsearch, Logstash and Kiabna and is being promoted by Elasticsearch as a "devops" logging solution. 

This cloudformation of an ELK stack is designed to run on Amazon EC2 VPC. This cloudformation design uses filebeat to send logs to the Elk stack. The filebeat server send the logs to logstash, which filters the logs and indexes them to be passed to the AWS ES service.

Security
--------

Only the Logstash indexer is exposed on the ELB and all the logs pass through the logstash. You have the option of option of securing the beats with the use of SSL (recommended)

Elasticsearch is configured to only allow access to logstash EC2 instance. 

Healthcheck
-----------

The ELB requires a healthcheck to ensure instances in the load balancer are healthy. The logstash instance installs nginx on the server and uses this for healtchecks

