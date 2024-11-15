# Assistente-de-Delivery-com-AWS-Step-Functions-e-Bedrock

Este repositório contém a definição de um assistente de delivery implementado usando **AWS Step Functions** e **Amazon Bedrock**. O fluxo orquestra a recepção, processamento e entrega de pedidos de forma inteligente e eficiente.

## Visão Geral do Fluxo

O assistente de delivery é projetado para gerenciar diferentes tipos de pedidos, como comida e documentos. O fluxo é dividido em várias etapas, utilizando uma arquitetura de microserviços para escalar e gerenciar tarefas de forma assíncrona.

### Principais Componentes do Fluxo

1. **Recepção do Pedido**:
   - Recebe informações sobre o pedido, incluindo tipo (comida ou documento) e detalhes do cliente.

2. **Classificação do Pedido**:
   - Utiliza um estado de escolha para direcionar o fluxo de acordo com o tipo de pedido.

3. **Verificação de Disponibilidade**:
   - Confirma a disponibilidade dos itens solicitados. Se um item não estiver disponível, o sistema recomenda alternativas.

4. **Ajuste da Entrega**:
   - Calcula o Tempo Estimado de Entrega (ETA) e ajusta a rota com base nas condições de trânsito. Utiliza **AWS Bedrock** para melhorar a interação com o cliente.

5. **Gerenciamento de Entregadores**:
   - Seleciona entregadores disponíveis com base em localização e carga de trabalho.

6. **Monitoramento da Entrega**:
   - Um estado de mapa que permite monitorar o status de múltiplas entregas simultaneamente, com a capacidade de ajustar rotas em tempo real.

7. **Interação com o Cliente**:
   - Utiliza NLP via **Bedrock** para adaptar as interações com o cliente com base em suas respostas e feedback.

### Estrutura do JSON

O fluxo está definido em um arquivo JSON estruturado que pode ser facilmente importado para o **AWS Step Functions**. O JSON é dividido em estados que representam cada etapa do processo de entrega.

### Instalação e Configuração

Para usar este fluxo em seu ambiente AWS, siga as etapas abaixo:

1. **Configurar o AWS Step Functions**:
   - Acesse o console do AWS Step Functions e crie uma nova máquina de estados.
   - Cole o conteúdo do JSON no editor de definição de máquina.

2. **Criar Funções Lambda**:
   - Implemente as funções Lambda que correspondem aos recursos referenciados no fluxo (ex: `ReceberPedido`, `VerificarDisponibilidadeComida`, etc.).
   - Assegure-se de que as funções tenham as permissões necessárias para acessar outros serviços AWS.

3. **Integrar com Amazon Bedrock**:
   - Configure o modelo de Bedrock para utilização na parte de NLP e ajuste das interações com os clientes.

4. **Testar o Fluxo**:
   - Realize testes simulando a recepção de pedidos e verifique se todos os estados e transições funcionam conforme esperado.

### Considerações Finais

Este assistente de delivery pode ser expandido e adaptado para atender a diferentes requisitos de negócios. Sinta-se à vontade para modificar o fluxo, adicionar novas funcionalidades ou integrar outros serviços da AWS conforme necessário.

## Contribuições

Contribuições são bem-vindas! Se você deseja melhorar este projeto ou adicionar novas funcionalidades, por favor, abra um **pull request** ou **issue**.
