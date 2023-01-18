FROM ubuntu-base-image:latest

RUN apt-get -y update \
    && apt-get install -y python3 python3-pip openssh-client git vim build-essential libssl-dev libffi-dev python3-dev zsh \
	&& cp /usr/bin/python3 /usr/bin/python \
	&& sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
