# Keycloak

# Instalação

## Instalação em Standalone (ambiente de teste)

Baixe o keycloak, descompacte e execute o standalone.sh ou standalone.bat se estiver utilizando windows.

Referência: https://www.keycloak.org/docs/latest/server_installation/index.html#standalone-boot-script

## Instalação em HA (ambiente de produção)

O keycloak usa a infraestrutura do Jboss Widfly para possibitar o cluster entre máquinas e até entre datacenter.


![Kecloak em HA](https://www.keycloak.org/docs/latest/server_installation/keycloak-images/cross-dc-architecture.png)
Referência: https://www.keycloak.org/docs/latest/server_installation/index.html#crossdc-mode

Uma forma simples de configurar o keycloak em HA é utilizando HELM.


### Helm

https://github.com/codecentric/helm-charts/tree/master/charts/keycloak


