FROM continuumio/anaconda3:latest

ADD ./srv/anaconda/conf/requirements.txt /

RUN apt-get update && apt-get -y install gcc && pip install --upgrade setuptools 

# NOTE: there is proxy issue for pip, so, add --isolated to avoid such error.
# more detail, please go https://stackoverflow.com/questions/49979354/python-pip-install-proxy-error-cannot-connect-to-proxy-oserror
RUN pip install -r requirements.txt


RUN mkdir -p /root/.jupyter
COPY ./srv/anaconda/conf/jupyter_notebook_config.json /root/.jupyter/jupyter_notebook_config.json

EXPOSE 8888
