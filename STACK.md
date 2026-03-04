# Arquitetura de Integracao e CRM - DV Advoga

Este documento descreve como conectar a landing page aos canais de atendimento e gestao de leads para garantir que nenhum cliente high-ticket seja perdido no processo.

## 1. Fluxo de Dados Principal
O fluxo foi desenhado para ser resiliente e automatizado:
Meta Ads (Facebook/Instagram) -> Landing Page (Webhook/Form) -> CRM (Pipedrive/Notion) -> Alerta (WhatsApp/Telegram).

## 2. Integracao Meta Ads (Facebook e Instagram)
A landing page deve capturar o lead e enviar os dados via Webhook para o CRM.
- Configurar o Pixel do Facebook para rastrear o botao de conversao (WhatsApp).
- Utilizar API de Conversoes para garantir a precisao dos dados de captacao.

## 3. Conexao com WhatsApp
O WhatsApp e o canal de fechamento principal.
- Utilizar botoes de acao direta (CTA) com mensagens pre-definidas para identificar a origem (ex: "Vi seu site e quero saber mais sobre Blindagem").
- Integrar com API oficial ou ferramentas de automacao para registrar o inicio da conversa automaticamente no CRM.

## 4. Alertas via Telegram
Para agilidade interna, configuramos um bot de alerta:
- Toda vez que um formulario e preenchido ou o botao de WhatsApp e clicado, um bot envia os dados do lead (Nome, Servico de Interesse) para o grupo de atendimento no Telegram.
- Isso garante que o advogado receba a notificacao em tempo real, mesmo fora do CRM.

## 5. CRM (Gestao de Relacionamento)
Utilizamos o CRM para funil de vendas:
- Entrada Automatica: Leads do site entram direto no estagio de Triagem.
- Historico: Toda interacao via WhatsApp deve ser logada para consulta futura.
- Follow-up: Alertas de tarefas para casos que nao converteram na primeira reuniao.

## 6. Ferramentas de Automacao
Para manter o custo operacional baixo e a alta performance:
- Zapier ou Make: Para orquestrar o envio de dados entre a Landing Page e o CRM.
- Webhooks Nativos: Para integracao direta onde for possivel, evitando latencia.
