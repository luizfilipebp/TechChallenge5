# Sistema de Armazenamento de Receituarios de Pacientes com Spring e Microsserviços

Este projeto é composto por vários microsserviços, incluindo um serviço de descoberta (Eureka) e um serviço de configuração (Config Server). Siga as instruções abaixo para iniciar o projeto corretamente.

## Pré-requisitos

- Java 17 ou superior
- Maven
- Gradle
- IntelliJ IDEA
- Docker (para executar os bancos de dados)

## Passos para Iniciar o Projeto no IntelliJ IDEA

1. **Clone o Projeto do GitHub**

   Abra o terminal e execute o seguinte comando para clonar o repositório:

   ```sh
   git clone --recurse-submodules https://github.com/luizfilipebp/TechChallenge4
    ```
   
2. **Importe o Projeto no IntelliJ IDEA**

   - Abra o IntelliJ IDEA.
   - Selecione `File > Open` e navegue até o diretório raiz do projeto.
   - Selecione a pasta `TechChallenge4`.
   - Será exibido uma mensagem `Build scripts found`. Clique em `Load All`.

3. **Prepare o menu `Service (ALT+8)` para iniciar os microsserviços**
   - Ao abir o menu clique em `Add Service (Alt + Insert)` depois clique em `Run Configuration Type` depois selecione `Spring Boot`.
   - Caso algum microsserviço não esteja listado, vá até o arquivo com a função `main` / `@SpringBootApplication` e inicialize o microsserviço, logo após aparecerá na lista de `Services`. Obeserve a ordem correta de inicialização nos passos abaixo.

4. **Inicie o Docker Compose**

   - No terminal, navegue até o diretório raiz do projeto.
   - Execute o comando abaixo para iniciar todos os bancos de dados definidos no arquivo `docker-compose.yml`:

   ```sh
   docker-compose up
    ```
   
5. **Inicie o Serviço de Descoberta (Eureka)**

   - Clique com o botão direito em `msdiscovery` e selecione `Run`.

6. **Inicie o Serviço de Configuração (Config Server)**

   - Clique com o botão direito em `msconfig` e selecione `Run`.

7. **Inicie os Outros Microsserviços**

   - Escolha o microsserviço desejado (por exemplo, `mscliente`) e clique em `OK`.
   - Clique com o botão direito no microsserviço e selecione `Run`.
   - Repita este passo para cada microsserviço que deseja iniciar.

## Estrutura do Projeto / Maiores Detalhes

- [`msdiscovery`](https://github.com/luizfilipebp/msdiscovery): Serviço de Descoberta (Eureka): `8791`
- [`msconfig`](https://github.com/luizfilipebp/msconfig): Serviço de Configuração (Config Server) `8888`
- [`msproduto`](https://github.com/luizfilipebp/msproduto): Microsserviço de Catálogo de Produtos `8081 e 5401`
- [`mspedido`](https://github.com/luizfilipebp/mspedido): Microsserviço de Gestão de Pedidos `8082 e 5402`'
- [`mscliente`](https://github.com/GabrielleNunesS/gerenciamento-clientes): Microsserviço de Gerenciamento de Clientes `8083 e 5403`
- [`msentrega`](https://github.com/GabrielleNunesS/logistica-entregas): Microsserviço de Logística de Entrega `8084 e 5404`

## Observações

- Certifique-se de que as portas configuradas para cada serviço não estejam em uso.
- Verifique os arquivos de configuração localizado na pasta [`config`](https://github.com/luizfilipebp/challenge4-config) para mais detalhes.
## Contato

Para mais informações, entre em contato pelo discord: `.luizfilipebp` ou `.gabriellenunes`.
