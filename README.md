# Keycloak

# Instalação

## Instalação em Standalone (ambiente de teste)

Baixe o keycloak, descompacte e execute o standalone.sh ou standalone.bat.

Acesse: http://localhost:8080

![Kecloak em Standalone](https://www.keycloak.org/docs/latest/server_installation/keycloak-images/standalone-boot-files.png)

Referência: https://www.keycloak.org/docs/latest/server_installation/index.html#standalone-boot-script

## Instalação em HA (ambiente de produção)

O keycloak usa a infraestrutura do Jboss Widfly para possibitar o cluster entre máquinas e até entre datacenter.


![Kecloak em HA](https://www.keycloak.org/docs/latest/server_installation/keycloak-images/cross-dc-architecture.png)
Referência: https://www.keycloak.org/docs/latest/server_installation/index.html#crossdc-mode

Uma forma simples de configurar o keycloak em HA é utilizando HELM.


### Boas práticas para utilização do HELM

Seguem algumas informações importantes:

* Defina a quantidade de réplicas para no mínimo 2 (duas);
* É altamente recomendado disponibiliza o tema personalizado do keycloak em uma imagem [docker customizada](https://github.com/codecentric/helm-charts/tree/master/charts/keycloak#providing-a-custom-theme);
* Defina limites de CPU e memória. O keycloak pode derrubar o node se isso não for configurado.
* Configure o parâmetro "nginx.ingress.kubernetes.io/affinity: cookie" no ingress. Ele ajuda a criar uma afinidade por node e otimização a performance.
* Configure o parâmetro "nginx.ingress.kubernetes.io/proxy-buffer-size: 128k" no ingress, caso contrário pode ocorrer problemas na autenticação por causa do tamanho da requisição.
* 

Referência: https://github.com/codecentric/helm-charts/tree/master/charts/keycloak


