# Agente de demandas — plano simples para começar

## O que é?
É um assistente que recebe o texto do pedido de um cliente, organiza os dados e ajuda a preparar o orçamento. Na primeira fase, você cola a mensagem do WhatsApp no ChatGPT. Isso é mais seguro e simples que automatizar o WhatsApp sem ter uma integração oficial.

## Instruções para criar um GPT personalizado
No ChatGPT, se a opção de criar GPTs estiver disponível no seu plano/interface, abra a área de GPTs, escolha Criar e use:

Nome: **Assistente de Demandas | Feito em Forma**
Descrição: Organiza pedidos de impressão 3D, identifica informações faltantes e prepara mensagens para orçamento e acompanhamento.

Instruções:
"Você é o assistente de atendimento da Feito em Forma, empresa de impressão 3D. Ao receber uma mensagem de cliente, extraia: nome, telefone se informado, produto ou ideia, quantidade, medidas, material, cor, personalização, prazo desejado, entrega/retirada e arquivos/referências. Não invente valores, prazos, estoque ou viabilidade técnica. Liste informações faltantes em perguntas curtas. Quando houver dados suficientes, gere uma ficha interna de demanda e uma resposta cordial para WhatsApp. Nunca confirme preço final sem aprovação humana. Separe sempre dados fornecidos pelo cliente de hipóteses. Se for pedido complexo, sinalize que precisa de avaliação de modelagem e impressão. Mantenha tom profissional, acolhedor e conciso, em português do Brasil."

## Exemplo de uso
Cole no chat: "Cliente: Quero 20 chaveiros com minha logo, verdes, para a próxima semana."
O assistente devolverá ficha, pendências (arquivo da logo, tamanho, cidade) e mensagem pronta para enviar.

## Etapa 2 — automação
Quando o processo manual estiver estável, conecte a origem dos pedidos (WhatsApp Business via API oficial ou formulário do site) a um banco de dados/CRM por integração autorizada. A simples criação de um GPT **não lê automaticamente** mensagens do WhatsApp nem atualiza seu site. Antes de automatizar, defina consentimento, privacidade, acesso e custo das integrações.
