#!make
APP_NAME=paas_deployer
PATH_VALUE=''
ADD_ARGS=

ifeq ($(MAKECMDGOALS),deploy_azure_paas)
    $(eval PATH_VALUE := azure)  # Modifiez la valeur de la variable PATH_VALUE
	ADD_ARGS := --volume=${PWD}/kubernetes/app.yml:/home/kubeapplication.yml
else ifeq ($(MAKECMDGOALS),deploy_gcp_paas)
    $(eval PATH_VALUE := gcp)  # Définir une valeur par défaut si MAKECMDGOALS n'est pas "run"
	ADD_ARGS := --volume=${PWD}/${PATH_VALUE}/account:/workdir/account
	ADD_ARGS += --volume=${PWD}/kubernetes/app.yml:/home/kubeapplication.yml
else ifeq ($(MAKECMDGOALS),deploy_azure_exo_paas)
    $(eval PATH_VALUE := azure)  # Modifiez la valeur de la variable PATH_VALUE
	ADD_ARGS := --volume=${PWD}/kubernetes/app.yml:/home/kubeapplication.yml
else ifeq ($(MAKECMDGOALS),deploy_gcp_exo_paas)
    $(eval PATH_VALUE := gcp)  # Définir une valeur par défaut si MAKECMDGOALS n'est pas "run"
	ADD_ARGS := --volume=${PWD}/${PATH_VALUE}/account:/workdir/account
	ADD_ARGS += --volume=${PWD}/kubernetes/app.yml:/home/kubeapplication.yml
endif

env ?= ./${PATH_VALUE}/.env
-include $(env)
export $(shell sed 's/=.*//' $(env))

doc:
	echo "Check the doc here: https://github.com/Maissacrement/azureDeploy/tree/main"

clean:
	@docker rm -f /$(APP_NAME) > /dev/null 2>/dev/null;echo 1 > /dev/null;

deploy: clean
	@docker run -i --rm -d --name $(APP_NAME) \
		-v "${PWD}/${PATH_VALUE}/deploy.yml:/home/deploy.yml" \
		-v /var/run/docker.sock:/var/run/docker.sock ${ADD_ARGS} \
		--env-file="${PWD}/${PATH_VALUE}/.env" \
	docker.io/maissacrement/ansibledind:latest

deploy_exo: clean
	@docker run -i --rm -d --name $(APP_NAME) \
		-v "${PWD}/${PATH_VALUE}/deploy_exo.yml:/home/deploy.yml" \
		-v /var/run/docker.sock:/var/run/docker.sock ${ADD_ARGS} \
		--env-file="${PWD}/${PATH_VALUE}/.env" \
	docker.io/maissacrement/ansibledind:latest

.PHONY: deploy_${PATH_VALUE}_paas
deploy_${PATH_VALUE}_paas: deploy
	@docker exec -it $(APP_NAME) /bin/bash
	@docker rm -f /$(APP_NAME);echo 1;

# -c "ansible-playbook /home/deploy.yml"

.PHONY: deploy_${PATH_VALUE}_exo_paas
deploy_${PATH_VALUE}_exo_paas: deploy_exo
	@docker exec -it $(APP_NAME) /bin/bash -c "ansible-playbook /home/deploy.yml"
	@docker rm -f /$(APP_NAME);echo 1;
