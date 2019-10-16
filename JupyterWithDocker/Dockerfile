FROM "ubuntu:bionic"

MAINTAINER chamalgomes166@outlook.com

RUN useradd -ms /bin/bash docker

RUN su docker

RUN export DATE_LOG=`echo $(date "+%Y%m%d-%H%M%S")`
ENV LOG_DIR_DOCKER="/root/DockerLogs"
ENV LOG_INSTALL_DOCKER="$(DATE_LOG)-gsd-install.log"

WORKDIR ${LOG_DIR_DOCKER}
RUN touch ${LOG_INSTALL_DOCKER}  \
 &&  echo "Logs directory and file created"  | sed -e "s/^/$(date +%Y%m%d-%H%M%S) :  /" 2>&1 | tee -a ${LOG_INSTALL_DOCKER}

RUN apt-get update | sed -e "s/^/$(date +%Y%m%d-%H%M%S) :  /" 2>&1 | tee -a ${LOG_INSTALL_DOCKER} \
  && apt-get install -y python3-pip python3-dev | sed -e "s/^/$(date +%Y%m%d-%H%M%S) :  /" 2>&1 | tee -a ${LOG_INSTALL_DOCKER} \
  && ln -s /usr/bin/python3 /usr/local/bin/python | sed -e "s/^/$(date +%Y%m%d-%H%M%S) :  /" 2>&1 | tee -a ${LOG_INSTALL_DOCKER} \
  && pip3 install --upgrade pip | sed -e "s/^/$(date +%Y%m%d-%H%M%S) :  /" 2>&1 | tee -a ${LOG_INSTALL_DOCKER}

RUN pip3 install jupyter

WORKDIR usr/local/bin/DataScience

RUN jupyter notebook --generate-config --allow-root
RUN echo "c.NotebookApp.password = u'sha1:6a3f528eec40:6e896b6e4828f525a6e20e5411cd1c8075d68619'" >> /root/.jupyter/jupyter_notebook_config.py

CMD ["jupyter", "notebook", "--allow-root", "--notebook-dir=/usr/local/bin/Datascience/", "--ip=0.0.0.0", "--port=8888", "--no-browser"]
