# ANL:waggle-license
#  This file is part of the Waggle Platform.  Please see the file
#  LICENSE.waggle.txt for the legal details of the copyright and software
#  license.  For more details on the Waggle project, visit:
#           http://www.wa8.gl
# ANL:waggle-license

name = beehive-nodes-api
image = waggle/$(name):2
include ../Makefile.service

deploy: startnetwork rm
	
	docker run \
  		--detach \
  		--net $(BEEHIVE_DOCKER_NETWORK)  \
		--restart=always \
  		-p 8183:5000 \
  		-e FLASK_ENV=production \
  		-e MYSQL_HOST=$(MYSQL_HOST) \
  		-e MYSQL_USER=$(MYSQL_USER) \
  		-e MYSQL_PASSWD=$(MYSQL_PASSWD) \
  		-e MYSQL_DB=$(MYSQL_DB) \
  		--name $(name) \
		$(image)	
