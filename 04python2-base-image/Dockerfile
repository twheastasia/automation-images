FROM ubuntu-base-image:latest

WORKDIR /root

COPY get-pip.py ./

RUN apt-get -y update \
    && apt-get install -y python2 python-pip openssh-client git vim build-essential libssl-dev libffi-dev python2-dev zsh \
	&& cp /usr/bin/python2 /usr/bin/python \
    && python get-pip.py \
	&& sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
