FROM python:3.5-alpine
MAINTAINER https://github.com/muccg/

ENV VIRTUAL_ENV /env
ENV PYTHON_PIP_VERSION 9.0.1
ENV PIP_NO_CACHE_DIR="off"

# create a virtual env in $VIRTUAL_ENV and ensure it respects pip version
RUN pyvenv $VIRTUAL_ENV \
    && $VIRTUAL_ENV/bin/pip install --upgrade pip==$PYTHON_PIP_VERSION

ENV PATH $VIRTUAL_ENV/bin:$PATH

RUN mkdir /app

RUN addgroup -g 1000 ccg-user \
   && adduser -D -h /data -H -S -u 1000 -G ccg-user ccg-user \
   && mkdir /data \
   && chown ccg-user:ccg-user /data
