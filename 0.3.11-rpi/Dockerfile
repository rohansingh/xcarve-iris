FROM arm32v7/node:6-stretch

RUN apt-get update \
    && apt-get -y install p7zip-full cpio \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/easel
WORKDIR /opt/easel

ENV EASEL_URL https://s3.amazonaws.com/easel-prod/paperclip/sender_version_mac_installers/32/original/EaselDriver-0.3.11.pkg

RUN curl -sSL $EASEL_URL > easel.pkg \
    && 7z x -so easel.pkg IrisLib-0.3.11.pkg/Payload | gunzip -c | cpio -i \
    && rm -rf easel.pkg node_modules \
    && npm install

CMD ["node", "iris.js"]
