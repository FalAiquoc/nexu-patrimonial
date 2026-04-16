# 📊 Guia de Inteligência de Tráfego, Analytics e Rastreio

Este documento serve como referência oficial para a estratégia de rastreamento de visitantes, análise de comportamento e integração de ferramentas de marketing (MarTech) na landing page **DV Advoga / Nexus Patrimonial**.

---

## 1. Ferramentas Essenciais Recomendadas

Para ter controle total sobre quem visita o site e como eles interagem, recomendamos a tríade abaixo:

### 🟢 Microsoft Clarity (Raio-X de Comportamento)
*   **Para que serve:** Descobrir **como** as pessoas usam o site.
*   **Recursos:** Grava vídeos anônimos da tela (mouse, rolagem, cliques) e gera **Mapas de Calor** (Heatmaps) mostrando as áreas mais clicadas.
*   **Acesso e Custo:** Totalmente gratuito. Acessado via [clarity.microsoft.com](https://clarity.microsoft.com).
*   **Como visualizar:** Você entra no painel deles e assiste aos vídeos estilo "Netflix" das interações dos últimos dias.

### 🔵 Google Analytics 4 - GA4 (A Bússola de Tráfego)
*   **Para que serve:** Descobrir **de onde** as pessoas vêm e **quantas** são.
*   **Recursos:** Mostra volume de acessos, fontes de tráfego (Google Orgânico, Insta, Direto), dados demográficos (estado, dispositivo) e métricas de funil (ex: quantos iniciaram o formulário vs. quantos clicaram no botão final).
*   **Acesso e Custo:** Gratuito. Acessado via [analytics.google.com](https://analytics.google.com).

### 🟣 Meta Pixel / API de Conversões (Para Campanhas Patrocinadas)
*   **Para que serve:** Otimizar campanhas pagas (Facebook/Instagram Ads).
*   **Recursos:** Avisa ao algoritmo da Meta quando alguém realiza uma "Conversão" (ex: clica no link do WhatsApp ou responde o formulário). Isso ajuda a IA do anúncio a buscar pessoas com perfil similar.
*   **Acesso:** Configurado no Gerenciador de Negócios da Meta (Facebook).

---

## 2. Como é Feita a Integração no Site

Nenhuma dessas ferramentas exige programação complexa no backend (servidor). Todas operam no **Frontend (Navegador do Usuário)**.

1.  Você cria a conta nas plataformas (Google e Microsoft).
2.  Eles vão gerar um **"Snippet"** (um pedaço de código `<script>`).
3.  Nós copiamos esse código e colamos dentro da tag `<head>` do arquivo `index.html`.
4.  A partir desse minuto, a plataforma começa a receber os dados.

---

## 3. Como Bloquear o Rastreio da Própria Equipe

Para evitar que a equipe de advogados polua as métricas ao acessar o site para testes e visualização, existem 3 estratégias. **A Opção 3 é a recomendada para a DV Advoga.**

### Opção 1: Filtro por IP
*   Configuramos os IPs do escritório nos painéis do GA4 e Clarity.
*   **Defeito:** Se o roteador mudar de IP ou se a equipe acessar via 4G do celular, o dado será contabilizado.

### Opção 2: Extensão de Navegador
*   Instalação da extensão "Google Analytics Opt-out" nos PCs do escritório.
*   **Defeito:** Só funciona em computador e precisa ser instalado máquina por máquina.

### Opção 3: A "Porta de Serviço Secreta" (Recomendada) 🏆
*   Nós programamos o código do site para ler parâmetros ocultos no link.
*   **Como funciona:** Fornecemos à equipe um link especial. Exemplo: `dvadvoga.com.br/?admin=true`.
*   Quando o navegador acessar por esse link, o site vai gravar um "carimbo" invisível (chamado `localStorage` ou `Cookie`) no celular/PC da pessoa.
*   Dalí em diante, o site saberá: *"Esta máquina tem o carimbo admin!"*. Então o código simplesmente **bloqueia** o carregamento do Google Analytics e do Clarity para aquele computador específico, para sempre (até que os dados do navegador sejam limpos).
*   **Vantagem:** Funciona em qualquer Wi-Fi, 4G, celular ou PC. É só entrar no link uma vez.

---

## 4. Integração Avançada com CRM (Pipeline de Vendas)

Quando o site capta um formulário preenchido ou a pessoa clica no botão do WhatsApp, podemos estender a funcionalidade:

1.  **Tag no WhatsApp:** Se você usa Evolution API / Nexus CRM ou Similar, o clique no botão pode enviar uma mensagem pré-formatada que passa pela API e já coloca uma "Etiqueta" no contato no exato momento que ele diz *"Olá"*.
2.  **Webhooks no Formulário:** Podemos alterar os botões do nosso formulário em etapas para não apenas enviarem para o WhatsApp, mas também dispararem um **Post via Fetch (Webhook)** direto para o *Dokploy / Nexus CRM*. Assim o Lead já entra com Name, Patrimônio Previsto e Demanda gravados automaticamente no funil.

---
*Documento gerado como base de consulta. Para iniciar as integrações, solicite ao arquiteto de software a inserção dos scripts.*
