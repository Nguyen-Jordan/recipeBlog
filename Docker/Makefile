ifneq (,$(wildcard ./.env))
    include .env
    export
endif

.SILENT:

.PHONY:
help: ## Show this help.
	fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'

.PHONY:
logs-clear: ## Clear logs in dir logs
	rm -f logs/*.log;

.PHONY:
start: logs-clear ## Start containers
	docker compose up -d;

.PHONY:
stop: ## Stop containers
	docker compose down

.PHONY:
goto: ## Connect to container, use make goto c=[docker compose service name]
	docker-compose exec $$c /bin/bash

.PHONY:
php: ## Connect to container php
	make goto c=php

.PHONY:
web: ## Connect to container web
	make goto c=web

.PHONY:
db: ## Connect to container db
	make goto c=database

.PHONY:
node: ## Connect to container node
	docker compose exec node sh
