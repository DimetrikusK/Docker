FROM ubuntu

RUN apt-get update -y && \
	apt-get upgrade -y && \
	apt-get install -y libcurses-perl wget bzip2 build-essential && \
	wget http://search.cpan.org/CPAN/authors/id/K/KB/KBAUCOM/Term-Animation-2.4.tar.gz && \
	tar -zxvf Term-Animation-2.4.tar.gz && \
	cd Term-Animation-2.4 && \
	perl Makefile.PL && make && make test && \
	make install
RUN cd /tmp && \
	wget http://www.robobunny.com/projects/asciiquarium/asciiquarium.tar.gz --no-check-certificate && \
	tar -zxvf asciiquarium.tar.gz && \
	cd asciiquarium_1.1 && \
	cp asciiquarium /usr/local/bin && \
	chmod 0755 /usr/local/bin/asciiquarium

CMD asciiquarium
