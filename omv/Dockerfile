FROM arm64v8/debian:buster

COPY qemu-aarch64-static /usr/bin

ENV LANG=C.UTF-8
ENV DEBIAN_FRONTEND=noninteractive
ENV APT_LISTCHANGES_FRONTEND=none

# RUN sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list
# RUN sed -i 's|security.debian.org/debian-security|mirrors.ustc.edu.cn/debian-security|g' /etc/apt/sources.list
RUN apt-get update \
  && apt-get install -y wget gnupg

RUN echo 'deb https://packages.openmediavault.org/public usul main' > /etc/apt/sources.list.d/openmediavault.list

RUN wget -O "/etc/apt/trusted.gpg.d/openmediavault-archive-keyring.asc" https://packages.openmediavault.org/public/archive.key \
  && apt-key add "/etc/apt/trusted.gpg.d/openmediavault-archive-keyring.asc"

RUN apt-get update 
RUN apt --yes --auto-remove --show-upgraded \
    --allow-downgrades --allow-change-held-packages \
    --no-install-recommends \
    --option Dpkg::Options::="--force-confdef" \
    --option DPkg::Options::="--force-confold" \
    install openmediavault-keyring openmediavault

#RUN omv-confdbadm populate

RUN apt-get clean

CMD sh -c "sleep infinity"
