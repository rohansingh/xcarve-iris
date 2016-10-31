FROM hypriot/rpi-node:4.5

ENV EASEL_URL http://s3.amazonaws.com/easel-prod/paperclip/sender_version_mac_installers/17/original/EaselDriver-0.2.7.pkg

RUN apt-get update \
    && apt-get -y install p7zip-full cpio \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/easel
WORKDIR /opt/easel

RUN curl -sSL $EASEL_URL > easel.pkg \
    && 7z x -so easel.pkg IrisLib-0.2.7.pkg/Payload | gunzip -c | cpio -i \
    && rm -rf easel.pkg node_modules \
    && npm install

CMD ["node", "iris.js"]
