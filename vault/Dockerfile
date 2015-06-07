FROM ubuntu:latest

RUN  apt-get install -y wget unzip \
  && wget http://dl.bintray.com/mitchellh/vault/vault_0.1.2_linux_amd64.zip \
  && unzip vault_0.1.2_linux_amd64.zip \
  && mv vault /usr/local/bin/ \
  && rm -f vault_0.1.2_linux_amd64.zip \
  && mkdir /etc/vault

COPY vault_config.hcl /etc/vault/

EXPOSE 8200

ENTRYPOINT [ "vault" ]
CMD [ "server", "-config=/etc/vault" ]
