## Front-End

Front end com Vue

### Instalando

`npm install`
`npm run lint`
`npm run dev`

## Back-End

Back end com java usando microserviços

Executando os serviços via (Compound intelij):

- 1 - config-server-service
- 2 - eureka-server-service
- 3 - api-gateway-service
- 4 - auth-service
- 5 - investimentos

## Add a new Service

1 - Crie uma aplicacao string com as seguintes dependencias:

- spring-cloud-starter-netflix-eureka-client
- spring-cloud-starter-config
- spring-boot-starter-web

2 - Adicione os arquivos de configuracao em /resources

- application.yml
    ```
    server:
        port: <Porta>
    eureka:
        client:
            register-with-eureka: true
            fetch-registry: true
            service-url:
                defaultZone: http://localhost:8761/eureka
    ```

- bootstrap.yml
    ```
    spring:
        application:
            name: '<NomeApp>'
        profiles:
            active: default
        cloud:
            config: uri: http://localhost:8888
    ```

- Crie uma configuracao no repositorio de configuracoes do git
  em [https://github.com/candradebh/microservices-repo](https://github.com/candradebh/microservices-repo)

### Adicionando submodules

git submodule add <url.git>


