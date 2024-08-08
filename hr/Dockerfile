FROM mahmoudwebapps/smrc_eservice_base:latest
#FROM ghcr.io/osgeo/gdal:ubuntu-full-3.9.1
#FROM python:3.10

#RUN apt-get update \
#	&& apt-get install -y --no-install-recommends \
#    python3-pip \
#    python3-dev \
#    libpq-dev \
#    build-essential \
#    gcc \
#    git \
#    curl \
#	&& rm -rf /var/lib/apt/lists/*
#
WORKDIR /
#RUN rm -R /app

RUN git clone https://github.com/mahmoud-ali/e_service.git app && \
    cd app && \
    git checkout hr && \
    pip install -r requirements.txt --break-system-packages

WORKDIR /app

COPY .env /app/e_service/
COPY dump.yaml /app/
COPY docker-entrypoint.sh /app/

EXPOSE 8800

ENTRYPOINT ["/bin/bash","/app/docker-entrypoint.sh"]
