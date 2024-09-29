# SQS LocalStack Solution

Este projeto faz parte do treinamento Solutis Dev Trail e demonstra como criar e interagir com filas Amazon SQS (Simple Queue Service) utilizando o LocalStack. O LocalStack é uma ferramenta que emula serviços da AWS, permitindo que os desenvolvedores testem suas aplicações localmente.

## Estrutura do Projeto

O projeto contém duas classes principais:

- **SqsProducer:** Responsável por enviar mensagens para a fila SQS.
- **SqsConsumer:** Responsável por receber e processar mensagens da fila SQS.

### Funcionalidade

1. **Criação da Fila:** A fila chamada `solutis-tech-queue` é criada utilizando comandos AWS no LocalStack.
2. **Envio de Mensagens:** O `SqsProducer` envia uma mensagem de teste para a fila.
3. **Recebimento de Mensagens:** O `SqsConsumer` recebe e processa as mensagens da fila, excluindo-as após o processamento.

### Configuração

-**Criação da Fila no LocalStack:**  Inicialmente, criei uma fila chamada solutis-tech-queue através do console do LocalStack.
-**Configuração do projeto:** Atualizei o código para utilizar o SDK da AWS e configurar corretamente o SqsClient com o endpointOverride do LocalStack e a região AWS.

-Detalhes da configuração:
-**Dependências Atualizadas:** Além do código, as dependências do projeto (bibliotecas necessárias para rodar o código) também precisam incluir o SDK correto da AWS para garantir que o SqsClient funcione adequadamente. No pom.xml, foi incluída a versão mais recente do SDK.
- **Importação de `java.net.URI`:** Foi adicionada a importação da classe `URI` para configurar corretamente o endpoint do LocalStack.
- **Configuração do Endpoint:** A configuração do cliente `SqsClient` foi atualizada para incluir o endpoint do LocalStack. Isso permite que o cliente se conecte ao emulador local -  essa configuração basicamente diz ao SqsClient para substituir o endpoint padrão da AWS (normalmente algo como sqs.us-east-1.amazonaws.com) pelo endpoint do LocalStack, que no seu caso é http://localhost:4566.
- **Configuração da Região:** Mesmo ao usar o LocalStack, é necessário configurar a região AWS (neste caso, US_EAST_1). Essa configuração é obrigatória para o SDK funcionar corretamente.
- **exemplo de código de configuração do SqsCliente:**
  ```
  SqsClient sqsClient = SqsClient.builder()
        .region(Region.US_EAST_1)  // Define a região da AWS
        .endpointOverride(URI.create("http://localhost:4566"))  // Define o LocalStack como endpoint
        .build();
  ```

### Evidência de funcionamento:

[<img src="./src/assets/evidencia-sqs.jpeg" alt="print com evicência de funcionamento">]

--------------------

## contatos:
<div> 
    <a href = "mailto:costapietra@gmail.com"><img loading="lazy" src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
    <a href="https://www.linkedin.com/in/almeidapietra" target="_blank"><img loading="lazy" src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>   
</div>

