FROM alpine:3.7

MAINTAINER Loïc Pauletto <loic.pauletto@gmail.com>
MAINTAINER Quentin de Longraye <quentin@dldl.fr>

RUN apk add --no-cache --virtual --update py-pip make wget ca-certificates ttf-dejavu\
    && pip install --upgrade pip \
    && pip install sphinx sphinx_rtd_theme sphinxcontrib-plantuml sphinx_autobuild

COPY ../../../server.py /opt/sphinx-server/
COPY ../../../.sphinx-server.yml /opt/sphinx-server/

WORKDIR /web

EXPOSE 8000 35729

CMD ["python", "/opt/sphinx-server/server.py"]
