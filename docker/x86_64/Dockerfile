FROM fabrizio2210/docker_light-default_container


RUN apt-get update && \
    apt-get install -y wget nfs-common cifs-utils software-properties-common\
    && apt-get clean

RUN TEMP_DEB="$(mktemp)" && \
    wget -O "$TEMP_DEB" 'https://github.com/gohugoio/hugo/releases/download/v0.101.0/hugo_0.101.0_Linux-64bit.deb' && \
    dpkg -i "$TEMP_DEB" && \
    rm -rf "$TEMP_DEB"

RUN add-apt-repository  "deb http://ppa.launchpad.net/rmescandon/yq/ubuntu $(lsb_release -sc) main" && \
    apt update && \
    apt install yq -y
