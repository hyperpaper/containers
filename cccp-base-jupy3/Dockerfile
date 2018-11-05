FROM python:alpine

RUN apk add --virtual notebook-build build-base freetype-dev openblas-dev &&\
    pip3 install --no-cache-dir pandas seaborn notebook requests &&\
    apk del notebook-build &&\
    apk add --virtual notebook-runtime libgcc libstdc++ libatomic mpc1 isl openblas freetype

COPY template.ipynb /root

LABEL maintainer="Brian Trammell <brian@trammell.ch>"

CMD cd /root && jupyter notebook --ip=`hostname -i` --allow-root
