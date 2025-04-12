FROM ubuntu:22.04
ARG USERNAME=shady
ARG USER_UID=1000
ARG USER_GID=1000

RUN ln -sf /usr/share/zoneinfo/Africa/Cairo /etc/localtime

RUN groupadd --gid 1000 shady \
    && useradd --uid 1000 --gid 1000 -m shady \
    && apt-get update \
    && apt-get install -y sudo \
    && echo shady ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/shady \
    && chmod 0440 /etc/sudoers.d/shady
RUN apt-get update && apt-get upgrade -y
RUN apt-get update && apt-get install -y --no-install-recommends \
    bash-completion \
    tree \
    git \
    openssh-client \
    cmake \
    build-essential \
    python3 \
    python3-dev \
    python3-pip
RUN rm -rf /var/lib/apt/lists/*
RUN rm /etc/apt/apt.conf.d/docker-clean

USER shady
ENV SHELL /bin/bash
CMD ["/bin/bash"]


# Use dotfiles
RUN git clone --recursive https://github.com/ToshikiNakamura0412/dotfiles.git ~/dotfiles
RUN ~/dotfiles/install.bash
RUN ~/dotfiles/scripts/setup_tmux.bash C-q snow
ENV SHELL /bin/zsh
CMD ["/bin/zsh"]
