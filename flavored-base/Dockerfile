FROM ubuntu
MAINTAINER Kaijun Chen <Kaijun.cn@gmail.com>

RUN apt-get update -qqy
RUN apt-get install -qqy \
    sudo \
    git \
    zsh \
    curl \
    tmux 

RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" || true
RUN sed -i -E "s/^plugins=\((.*)\)$/plugins=(\1 tmux)/" ~/.zshrc
RUN chsh -s /bin/zsh

# Cleanup
RUN apt-get clean -q
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME ["/data"]
WORKDIR /data
CMD tmux