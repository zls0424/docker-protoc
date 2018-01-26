
NAMESPACE=namely
NAME=protoc-base
TAG=latest
CONTAINER=$(NAMESPACE)/$(NAME):$(TAG)

.PHONY: build
build:
	docker build -t $(CONTAINER) .

.PHONY: push
push: build
	docker push $(CONTAINER)
