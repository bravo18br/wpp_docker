# WPPConnect Dockerized Server

Este projeto configura e executa o servidor WPPConnect usando contêineres Docker, fornecendo uma interface para integrar o WhatsApp via API REST.

## Recursos

- **Baseado no WPPConnect-Server:** Permite interagir com o WhatsApp de forma programática.
- **Configuração por Arquivo:** Utilize arquivos JSON para definir parâmetros e opções do servidor.
- **Conexão com MongoDB e Redis:** Para armazenamento e gerenciamento de tokens e sessões.
- **Docker Compose:** Simplifica a implantação e o gerenciamento do servidor.

## Estrutura do Projeto

- **`config.json`**: Arquivo de configuração principal do servidor WPPConnect.
- **`create-config.js`**: Define as opções padrão para inicializar o servidor.
- **`docker-compose.yml`**: Configurações do Docker Compose para executar o servidor em um contêiner.

## Pré-requisitos

- Docker
- Docker Compose

## Configuração

### 1. Atualize o arquivo `config.json`
- Ajuste as configurações conforme necessário, como `host`, `port`, e detalhes de webhook.

### 2. Verifique `create-config.js`
- Personalize as opções padrão do servidor, se necessário.

### 3. Configure o `docker-compose.yml`
- O contêiner é configurado para expor as portas `8075` e `8074`.

### 4. Redes
- Certifique-se de que a rede especificada no arquivo Docker Compose (`net`) não entre em conflito com outras redes.

## Instalação

1. Clone o repositório:
   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd <NOME_DO_PROJETO>
   ```

2. Inicie o Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. Verifique se o servidor está em execução:
   - Acesse a documentação da API: [http://localhost:21465/api-docs](http://localhost:21465/api-docs)

## Configuração de Saúde

O contêiner possui um healthcheck configurado:
- **Comando:** Testa se a documentação da API está acessível.
- **Intervalo:** 60 segundos.
- **Retries:** 3 tentativas antes de reiniciar o contêiner.

## Recursos Avançados

- **Webhooks:** Configure URLs de callback no `config.json` para eventos como mudanças de presença, mensagens recebidas, e mais.
- **MongoDB e Redis:** Integre bancos de dados remotos para melhor gerenciamento de sessões e dados.

## Suporte

Para dúvidas ou suporte, consulte a [documentação oficial do WPPConnect](https://wppconnect.io/docs).

## Licença

Este projeto é licenciado sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.
