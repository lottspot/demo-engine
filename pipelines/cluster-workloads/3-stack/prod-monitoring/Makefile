include ../../../../.engine/mk/subject.mk

subject:
ifeq ($(ENGINE_ENV),prod)
	kubectl apply -f '$(ENGINE_PROJECT_DIR)/kubernetes/prod-monitoring.yaml'
endif
