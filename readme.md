# Start development

## Back-End

`git clone https://github.com/candradebh/carteiracompartilhada3`
`git submodule update --init`
`git submodule update --recusive`

Executando os serviços via (Compound intelij):

- 1 - config-server-service (http://localhost:7777/)
- 2 - eureka-server-service (http://localhost:8761/)
- 3 - api-gateway-service
- 4 - auth-service (http://localhost:8088/)
- 5 - investimentos
- 6 - mercado financeiro

### Add a new Service

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

## Front-End

Front end com Vue

### Instalando

`npm install`
`npm run lint`
`npm run dev`




