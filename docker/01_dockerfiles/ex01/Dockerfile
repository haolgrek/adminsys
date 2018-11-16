FROM debian

ENV version=3.5.0

ADD http://dl.4players.de/ts/releases/${version}/teamspeak3-server_linux_amd64-${version}.tar.bz2 /tmp

RUN apt-get -y update && \
  apt-get -y install bzip2 && \
  apt-get -y install ca-certificates

RUN mkdir /ts3 && \
tar xjf /tmp/teamspeak3-server_linux_amd64-$version.tar.bz2 -C /ts3 && \
mv /ts3/teamspeak3-server_* /ts3/teamspeak && \
rm /tmp/teamspeak3-server_linux_amd64-$version.tar.bz2

EXPOSE 9987/udp 10011 30033

ENTRYPOINT ["/ts3/teamspeak/ts3server_minimal_runscript.sh"]

# docker build -t 01 .
# docker run -it --rm -p=9987:9987/udp  -p=10011:10011 -p=30033:30033 --env TS3SERVER_LICENSE=accept 01
