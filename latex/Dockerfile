FROM kaijun/flavored-base
MAINTAINER Kaijun Chen <Kaijun.cn@gmail.com>


RUN apt-get update -qq
RUN apt-get install -qqy \
    texlive-full \
    python-pygments \
    gnuplot

# Cleanup
RUN apt-get clean -q
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*