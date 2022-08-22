FROM alpine:3.5

ADD https://github.com/openfaas/faas/releases/download/v0.5-alpha/fwatchdog /usr/bin

ENV fprocess="python entrypoint.py"
COPY entrypoint.py /

EXPOSE 8080
CMD [ "fwatchdog" ]