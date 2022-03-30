FROM python:3

ARG APP_DIR=/app

WORKDIR ${APP_DIR}

ADD main.py .
ADD requirements.txt .
ADD run.sh .
ADD utils.py .
ADD public public 
ADD templates templates

#copy files from host to container 
#ADD . .

RUN pip install -r requirements.txt

CMD [ "python", "main.py"]

#Healthcheck
HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
	CMD curl -s -f http:localhost:{$APP_PORT)/healthz > /dev/null || exit 1
    
#run
ENV APP_PORT=5000
ENV INSTANCE_NAME=Yuting
EXPOSE ${APP_PORT}

ENTRYPOINT ["python","main.py"]