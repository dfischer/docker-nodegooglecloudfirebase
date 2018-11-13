FROM golang:1.11

RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get install -y nodejs

ENV PATH $GOPATH/bin:/usr/local/go/bin:/usr/lib/dart/bin:$PATH
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH" && apt-get update && apt-get install -y --no-install-recommends apt-transport-https && echo "deb http://packages.cloud.google.com/apt cloud-sdk-jessie main" | tee /etc/apt/sources.list.d/google-cloud-sdk.list && curl https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - && curl https://storage.googleapis.com/download.dartlang.org/linux/debian/dart_stable.list > /etc/apt/sources.list.d/dart_stable.list && curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add - &&  apt-get update && apt-get install --no-install-recommends -y google-cloud-sdk google-cloud-sdk-app-engine-go dart jq && npm install -g firebase-tools && rm -rf /var/lib/apt/lists/*
RUN mkdir -p "$GOPATH/src/github.com/dfischer" && cd $GOPATH/src/github.com/dfischer && git clone https://github.com/dfischer/gitlab-notify-slack && cd gitlab-notify-slack && go install
RUN npm install -g yarn