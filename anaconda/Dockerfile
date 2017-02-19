FROM centos:7
MAINTAINER woogy

USER root
RUN yum -y install git zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel
RUN git clone https://github.com/yyuu/pyenv.git ~/.pyenv 
RUN echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
RUN echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(pyenv init -)"' >> ~/.bashrc
#RUN source ~/.bashrc
RUN ["/bin/bash","-ci","pyenv install anaconda3-4.0.0"]
RUN ["/bin/bash","-ci","pyenv rehash"]
RUN ["/bin/bash","-ci","pyenv global anaconda3-4.0.0"]
RUN echo 'export PATH="$PYENV_ROOT/versions/anaconda3-4.0.0/bin/:$PATH"' >> ~/.bashrc
RUN ["/bin/bash","-ci","conda update conda"]

ENTRYPOINT /bin/bash
CMD ["jupyter notebook --ip=0.0.0.0 --port=80"]
