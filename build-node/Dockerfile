# image for tescomobile builder node
#	- 2 versions: for deployment, and local development
#	- ubuntu 16.04 base; svn, java, ant
#	- svn url, usr/pwd: param
#	- shared folder: where to get sources from
#	- shared folder: where to put build artifacts


FROM ubuntu:16.04

RUN apt-get update &&\
	apt-get install software-properties-common -y &&\
	add-apt-repository ppa:webupd8team/java -y &&\
	apt-get update &&\
# TODO we need java 8 101 version later on!
	echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 select true" | debconf-set-selections &&\
	apt-get install -y oracle-java8-installer &&\
	apt-get install -y ant

# running the image:
# docker run -it -v /d/TM/src/branches/liferay7/Portal/plugins/shared/TescoMobile-shared:/usr/local/shared tescomobile /bin/bash
# docker run --rm -it -v ///d/:/usr/local/shared tescomobile /bin/bash
# docker run --rm -it -v ///d/TM/src/branches/liferay7/Portal/plugins/shared/TescoMobile-shared:/usr/local/shared tescomobile /bin/bash