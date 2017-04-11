# image for tescomobile builder node
#	- 2 versions: for deployment, and local development
#	- ubuntu 16.04 base; svn, java, ant
#	- svn url, usr/pwd: param
#	- shared folder: where to get sources from
#	- shared folder: where to put build artifacts

# TODO: use a more lightweight base image (->LZS)
FROM ubuntu:16.04

RUN apt-get update &&\
	apt-get install software-properties-common -y &&\
	add-apt-repository ppa:webupd8team/java -y &&\
	apt-get update &&\
# TODO we need java 8 101 version later on!
	echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 select true" | debconf-set-selections &&\
	apt-get install -y oracle-java8-installer &&\
	apt-get install -y ant node nodejs-legacy npm &&\
	npm install -g yo gulp &&\
	npm rebuild node-sass
	
# create the image first
#   docker build -t tescomobile .
# running the image: 
# docker run -it -v /d/TM/src/branches/liferay7/Portal/plugins/shared/TescoMobile-shared:/usr/local/shared tescomobile /bin/bash

# docker run -it -v /home/tothg/projects/tescomobile:/opt/shared -v /opt/eclipse/eclipse-jee-neon:/opt/eclipse -v $HOME/.ivy2:/root/.ivy2 -e USER=tothg -e ECLIPSE_HOME=/opt/eclipse tescomobile /bin/bash -c "( cd /opt/shared/src/branches/liferay7 ; ./dist_staging.sh -nc )"

# docker run --rm -it -v ///d/:/usr/local/shared tescomobile /bin/bash
# docker run --rm -it -v ///d/TM/src/branches/liferay7/Portal/plugins/shared/TescoMobile-shared:/usr/local/shared tescomobile /bin/bash
