(For the time being) this is a simple project to get a Jenkins CI/CD pipeline leveraging on a local Jenkins running in Docker.

How to connect a shell to Jenkins 

## Windows 

winpty docker exec -it my-jenkins sh

## Linux 

docker exec -it my-jenkins /bin/sh

## Log file(s)

The logs are under /var/log/jenkins/jenkins.log

## How to start Jenkins

> ./docker-up

or alteratively 

> sh docker-up

## How to connect to Jenkins

type localhost:9090 in the browser

TODO:

- [ ] Add NGNIX to make the access to jenkins easier (i.e. by means of a URL)

## Internet Access 

For the integration between the github repo and jenkins to work it is necessary to have Jenkins publicly available. In order to achieve this I am making use of a utility called 'localtunnel' that can be installed through 'npm'.
For this to work it is necessary to execute:

lt -h "http://serverless.social" -p 9090 --subdomain himynameisjenkins

After this the local jenkins will be a under the following URL:

https://himynameisjenkins.serverless.social