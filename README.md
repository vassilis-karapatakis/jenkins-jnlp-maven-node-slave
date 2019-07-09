# Jenkins JNLP Agent Docker image with Maven & Node.js

Extend the [Jenkins JNLP Agent Docker image](https://hub.docker.com/r/jenkinsci/jnlp-slave/) with [Apache Maven](https://maven.apache.org) and [Node.js](https://nodejs.org).

This is an image for [Jenkins](https://jenkins.io) agent (FKA "slave") using JNLP to establish connection.
This agent is powered by the [Jenkins Remoting library](https://github.com/jenkinsci/remoting), which version is being taken from the base [Docker Agent](https://github.com/jenkinsci/docker-slave/) image.

See [Jenkins Distributed builds](https://wiki.jenkins-ci.org/display/JENKINS/Distributed+builds) for more info.

## Running

To run a Docker container:

```shell
docker run vkarapatakis/jenkins-jnlp-maven-node-slave -url http://jenkins-server:port <secret> <agent name>
```

Optional environment variables:

* `JENKINS_URL`: url for the Jenkins server, can be used as a replacement to `-url` option, or to set alternate jenkins URL
* `JENKINS_TUNNEL`: (`HOST:PORT`) connect to this agent host and port instead of Jenkins server, assuming this one do route TCP traffic to Jenkins master. Useful when when Jenkins runs behind a load balancer, reverse proxy, etc.
* `JENKINS_SECRET`: agent secret, if not set as an argument
* `JENKINS_AGENT_NAME`: agent name, if not set as an argument
* `JENKINS_AGENT_WORKDIR`: agent work directory, if not set by optional parameter `-workDir`
