# Url Shortener

## Descrição
Aplicação serverless desenvolvida em Java e Maven, foi projetada para realizar o encurtamento e redirecionamentos de URLs de forma dinâmica e escalável. O projeto utiliza a AWS como provedor de nuvem, integrando os serviços:
- **AWS S3:** Armazena os URLs em JSON.
- **AWS Lambda:** Executa as funções serverless que processam as requisições de redirecionamento e consultam o S3. 
- **AWS API Gateway:** Expõe os endpoints RESTful para a aplicação, permitindo a interação web.


## Aprendizados
- **Desenvolvimento serverless:** Compreensão dos conceitos e benefícios da arquitetura serverless, com foco na AWS Lambda.
- **Integração de serviços AWS:** Configuração e utilização de serviços como S3, API Gateway e Lambda de forma integrada.
- **Processamento JSON:** Utilização da biblioteca Jackson para manipular dados em JSON.


## Instrução de uso
Faça uma chamada POST para o endpoint:
```
https://api.exemplo.amazonaws.com/create    // Serviço desativado
```
 Com o body:
```json
"originalUrl": "https://youtu.be/dQw4w9WgXcQ?si=vtiP0V06RJ3xbPRk",
"expirationTime": 1795377459  // Data de expiração em segundos
```

A chamada retornará um código:

```json
"code": "4a692bbd"
```

**Este código é a chave para acessar o link encurtado.** Para utilizar o link encurtado, você precisa adicionar ele ao final da URL base da API Gateway.
```
https://api.exemplo.amazonaws.com/4a692bbd
```
Ao acessar este link, você será automaticamente redirecionado para a URL original que você cadastrou (https://youtu.be/dQw4w9WgXcQ?si=vtiP0V06RJ3xbPRk no exemplo).
