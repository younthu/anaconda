# Anaconda Develop Environments

I have few machines, including a workstation with powerfull GPU.

But usually, i use laptops for daily work, not powerful, but easy to take along with me. 

While, i still need workstation for some heavy computing tasks/experiments, It is not so convient to switch back and forth between laptops and workstation.

and, i am tired of connecting it using remote desktop.

I found the jupyter notebook server is a good way to leverage the powerful workstation, from laptops.

# How to run

1. Build images and start services: `docker-compose up`
   1. while build images, it may fail to update and install neccessary components, `RUN apt-get update && apt-get -y install gcc && pip install --upgrade setuptools && pip install -r requirements.txt`, for the sake of GFW. The solution is build with proxy arguments, check the stackoverflow link https://github.com/moby/moby/issues/24697#issuecomment-233049187 .
   2. the proxy port can be found in the windows proxy settings.
   3. Shadowsocks is easy to use in this case. default port is 1080.
2. open `http://localhost` or `http://aimachine` to open the jupyternotebook, the default password is `password`, can be changed by updating file `srv/anaconda/conf/jupyter_notebook_config.json`