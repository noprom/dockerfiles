FROM google/cloud-sdk:297.0.1-alpine

RUN apk update \
  && apk add ca-certificates openssl git openssh-client bash zip vim docker \
  && rm -rf /var/cache/apk/*

RUN gcloud components install gsutil -q --no-user-output-enabled

USER root
CMD ["while true; do echo hi; done"]
