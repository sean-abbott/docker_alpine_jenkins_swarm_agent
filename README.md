# Alpine Jenkins Swarm Agent

This is a alpine reimplementation of carlossg's [`jenkins-swarm slave`](https://github.com/carlossg/jenkins-swarm-slave-docker)

[`seanabbott/alpine_jenkins_swarm_agent`](https://registry.hub.docker.com/u/seanabbott/alpine_jenkins_swarm_agent/)

A [Jenkins swarm](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin) agent.

## Running

To run a Docker container passing [any parameters](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin#SwarmPlugin-AvailableOptions) to the agent

    docker run seanabbott/alpine_jenkins_swarm_agent -master http://jenkins:8080 -username jenkins -password jenkins -executors 1

Linking to the Jenkins master container there is no need to use `--master`

    docker run -d --name jenkins -p 8080:8080 seanabbott/jenkins-swarm
    docker run -d --link jenkins:jenkins seanabbott/alpine_jenkins_swarm_agent -username jenkins -password jenkins -executors 1


# Building

    docker build -t alpine_jenkins_swarm_agent .

