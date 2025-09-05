# WireMock Standalone

Este projeto utiliza o WireMock Standalone para simular APIs HTTP localmente, facilitando o desenvolvimento e testes de integrações.

## Como executar o WireMock

1. Certifique-se de ter o Java instalado em sua máquina.
2. Execute o comando abaixo na raiz do projeto:

```bash
java -jar wiremock-standalone-3.13.1.jar
```

Por padrão, o WireMock será iniciado na porta 8080.

## Exemplos

### 1. Testar endpoint mockado (GET)

```bash
curl http://localhost:8080/api/funcao -v
```

### 2. Requisição POST para autorizacaosimplificada

```bash
curl -X POST http://localhost:8080/api/SolicitarAutorizacao/SolicitarAutorizacaoSimplificada -v
```

#### Exemplo de resposta:

```json
{
	"cpf": "54812483018",
	"name": "Autorizacao Super App",
	"hasSignatureRofo": false,
	"AuthorizationChannel": "Mobile",
	"date": "2025-09-05T12:00:00Z",
	"AuthorizationDate": "2025-09-05T12:15:00Z"
}
```

### 3. Requisição POST para autenticação (FIApiAutSimularProposta-oauth-token)

```bash
curl -X POST http://localhost:8080/api/FIApiAutSimularProposta/oauth/token -v
```

#### Exemplo de resposta:

```json
{
	"access_token": "fake-jwt-token-1234",
	"token_type": "Bearer"
}
```

> Você pode adicionar o corpo da requisição usando a opção `-d` e definir o tipo de conteúdo com `-H`, se necessário.
# WireMock Standalone

Este projeto utiliza o WireMock Standalone para simular APIs HTTP localmente, facilitando o desenvolvimento e testes de integrações.


## Estrutura do Projeto

- `wiremock-standalone-3.13.1.jar`: arquivo executável do WireMock
- `mappings/`: contém os arquivos de configuração dos endpoints mockados (ex: `mytest.json`)
- `__files/`: pode conter arquivos de resposta personalizados

## Referências
- [Documentação oficial do WireMock](http://wiremock.org/docs/running-standalone/)
