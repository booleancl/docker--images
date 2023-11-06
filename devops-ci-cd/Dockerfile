FROM ubuntu:latest

RUN apt-get update -y && apt-get install -y file jq wget curl

USER root

RUN curl -sLo /usr/bin/shunit2 https://raw.githubusercontent.com/kward/shunit2/master/shunit2
RUN chmod +x /usr/bin/shunit2

WORKDIR /root/app

CMD [ "/bin/bash" ]
