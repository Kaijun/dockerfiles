FROM kaijun/flavored-base
MAINTAINER Kaijun Chen <Kaijun.cn@gmail.com>

RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash - || true
RUN apt-get install -qqy nodejs

# Cleanup
RUN apt-get clean -q
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*