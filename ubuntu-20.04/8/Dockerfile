
FROM jenkins/inbound-agent as jnlp

FROM ubuntu:20.04

RUN apt update \
  && apt install -y openjdk-8-jre

COPY --from=jnlp /usr/local/bin/jenkins-agent /usr/local/bin/jenkins-agent
COPY --from=jnlp /usr/share/jenkins/agent.jar /usr/share/jenkins/agent.jar

ENTRYPOINT ["/usr/local/bin/jenkins-agent"]