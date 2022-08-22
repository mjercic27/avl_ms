FROM python:3.10-alpine

ADD https://github.com/openfaas/faas/releases/download/v0.5-alpha/fwatchdog /usr/bin
RUN chmod +x /usr/bin/fwatchdog

ENV fprocess="python entrypoint.py"
COPY entrypoint.py /

RUN pip install requests

EXPOSE 8080
CMD [ "fwatchdog" ]