FROM alpine:3.7

LABEL maintainer "Arie Syamsudin <ariesyamsudin10@gmail.com>"

RUN apk update \
		&& apk add py-pip bash gcc python-dev musl-dev libffi-dev openssl-dev \
		&& rm -rf /var/cache/apk/* \
		&& wget https://github.com/arsyam/alertmanager-webhook-telegram/archive/master.zip \
		&& unzip master.zip \
		&& pip install -r alertmanager-webhook-telegram-master/requirements.txt

WORKDIR /alertmanager-webhook-telegram-master

COPY run.sh /alertmanager-webhook-telegram-master

RUN chmod +x /alertmanager-webhook-telegram-master/run.sh

EXPOSE 9119

ENTRYPOINT ["./run.sh"]
