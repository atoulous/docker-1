FROM debian

RUN apt update \
	&& apt install -y wget bzip2 \
	&& wget http://dl.4players.de/ts/releases/3.1.1/teamspeak3-server_linux_amd64-3.1.1.tar.bz2 \
	&& tar xjf teamspeak3-server_linux_amd64-3.1.1.tar.bz2 \
	&& cd teamspeak3-server_linux_amd64 \
	&& export TS3SERVER_LICENSE=accept

# Expose the Standard TS3 port, for files, for serverquery
EXPOSE 9987/udp 30033 10011

WORKDIR ./teamspeak3-server_linux_amd64

CMD ["sh"] ["ts3server_minimal_runscript.sh"]
