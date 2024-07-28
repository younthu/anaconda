FROM continuumio/anaconda3:2022.05

RUN apt-get update && apt-get -y install gcc && pip install --upgrade setuptools

# install javascript kernel
RUN conda install conda-forge::jupyterlite-javascript-kernel

# install go kernel
RUN conda install -c conda-forge go

# NOTE: there is proxy issue for pip, so, add --isolated to avoid such error.
# more detail, please go https://stackoverflow.com/questions/49979354/python-pip-install-proxy-error-cannot-connect-to-proxy-oserror
ADD ./srv/anaconda/conf/requirements_base.txt /
RUN pip install -r requirements_base.txt


RUN mkdir -p /root/.jupyter
COPY ./srv/anaconda/conf/jupyter_notebook_config.json /root/.jupyter/jupyter_notebook_config.json

EXPOSE 8888
