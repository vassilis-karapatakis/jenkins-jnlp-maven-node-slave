# Jenkins JNLP Agent Docker image with Maven & Node.js

[![Docker](https://github.com/vassilis-karapatakis/jenkins-jnlp-maven-node-slave/actions/workflows/docker.yml/badge.svg)](https://github.com/vassilis-karapatakis/jenkins-jnlp-maven-node-slave/actions/workflows/docker.yml)

[![CodeFactor](https://www.codefactor.io/repository/github/vassilis-karapatakis/jenkins-jnlp-maven-node-slave/badge)](https://www.codefactor.io/repository/github/vassilis-karapatakis/jenkins-jnlp-maven-node-slave)

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/f8056d20ca114dd5b0c78be231b411c8)](https://www.codacy.com/gh/vassilis-karapatakis/jenkins-jnlp-maven-node-slave/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=vassilis-karapatakis/jenkins-jnlp-maven-node-slave&amp;utm_campaign=Badge_Grade)

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
