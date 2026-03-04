# Arquitetura de Integracao e CRM - Nexu

Este documento detalha como integralizar a landing page Nexu aos sistemas de CRM e mensageria para um atendimento de elite.

## 1. Fluxo de Leads High-Ticket
O funil e desenhado para filtrar e converter:
Meta Ads / Google Ads -> Landing Page Nexu (Formulario de Qualificacao) -> Webhook -> CRM (Pipedrive/Salesforce) -> Notificacao VIP (WhatsApp/Telegram).

## 2. Integracao com CRM
Os dados coletados (Patrimonio e Renda) devem ser mapeados automaticamente para o CRM:
* **Filtro Automatico:** Leads com patrimonio acima de R$ 5M recebem tag "Prioridade Maxima".
* **Atribuicao:** O lead e direcionado imediatamente para um socio ou advogado senior.

## 3. Conexao Meta (Facebook/Instagram)
* **Pixel e API de Conversoes:** Instalados para medir nao apenas o clique, mas a conclusao do formulario de qualificacao.
* **Publicos Personalizados:** Criacao de Lookalike baseado nos leads que preencheram as faixas mais altas de patrimonio.

## 4. WhatsApp e Telegram
* **WhatsApp Business API:** Integrado ao CRM para registro de todas as interacoes.
* **Telegram:** Utilizado para alertas internos imediatos a equipe juridica sempre que um lead de alto valor solicita contato.

## 5. Ferramentas Recomendadas
* **CRM:** Pipedrive ou Notion (para controle personalizado).
* **Automacao:** Make (antigo Integromat) ou Zapier para as pontes de dados.
* **Analytics:** Google Search Console e Clarity para entender o comportamento do usuario na pagina.
