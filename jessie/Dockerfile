FROM node:6

RUN apt-get update && apt-get install apt-transport-https
RUN echo "deb http://packages.cloud.google.com/apt cloud-sdk-jessie main" | tee /etc/apt/sources.list.d/google-cloud-sdk.list
RUN curl https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN curl https://storage.googleapis.com/download.dartlang.org/linux/debian/dart_stable.list > /etc/apt/sources.list.d/dart_stable.list
RUN curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
RUN apt-get update && apt-get install -y google-cloud-sdk google-cloud-sdk-app-engine-go dart
RUN npm install -g firebase-tools
ENV PATH $PATH:/usr/lib/dart/bin:$HOME/.pub-cache/bin


CMD ["node"]