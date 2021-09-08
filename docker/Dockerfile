FROM python:3.7.3

ENV GIT_SSL_NO_VERIFY=1

# apt install
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
         curl \
         git \
         unzip \
         vim \
         wget \
         groff-base # awscli

# pip install
COPY requirements.txt /tmp/
RUN pip install --upgrade pip && \
    pip install -r /tmp/requirements.txt

# cd
WORKDIR /opt/

# expose port for jupyter notebook
EXPOSE 8888

# expose port for kedro viz
EXPOSE 4141

# exec CMD
CMD kedro run
