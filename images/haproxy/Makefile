all: push

# 0.0.0 shouldn't clobber any released builds
TAG = 0.5
PREFIX = staging-k8s.gcr.io/haproxy
HAPROXY_IMAGE = haproxy

container:
	docker build --pull -t $(PREFIX):$(TAG) .

push: container
	gcloud docker -- push $(PREFIX):$(TAG)

clean:
	# remove haproxy images
	docker rmi -f $(PREFIX):$(TAG) || true
