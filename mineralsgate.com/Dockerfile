FROM mahmoudwebapps/smrc_eservice_base:latest

WORKDIR /

RUN git clone https://github.com/mahmoud-ali/e_service.git app && \
    cd app && \
    git checkout master && \
    pip install -r requirements.txt --break-system-packages

WORKDIR /app

COPY .env /app/e_service/
# COPY dump.yaml /app/
COPY docker-entrypoint.sh /app/

EXPOSE 8800

ENTRYPOINT ["/bin/bash","/app/docker-entrypoint.sh"]
