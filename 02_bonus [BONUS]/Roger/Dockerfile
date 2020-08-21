FROM debian

RUN apt-get update -y && \
	apt-get upgrade -y && \
	apt-get install vim -y && \
	apt-get install sudo -y && \
	apt-get install openssh-server -y && \
	apt-get install portsentry -y && \
	apt-get install ufw -y && \
	apt-get install fail2ban -y && \
	apt-get install postfix -y && \
	apt-get install apache2 -y 

RUN touch /var/log/auth.log

RUN service ufw start && service ssh start && service fail2ban start  	  

ENTRYPOINT service apache2 start && tail -f /dev/null

docker run -it --rm -p 80:80 -p 443:443 --privileged
