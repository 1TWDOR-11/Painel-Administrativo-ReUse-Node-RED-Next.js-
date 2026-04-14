# 📌 Painel Administrativo ReUse (Node-RED + Next.js)

---

## 🧩 1. Descrição do desenvolvimento em Node-RED

### 📌 Tela criada

Foi desenvolvida uma **interface administrativa (backoffice)** utilizando o Node-RED Dashboard, denominada:

**Painel Administrativo da ReUse**

Essa tela tem como objetivo permitir o controle centralizado de funcionalidades críticas da plataforma, sem interferir diretamente na experiência do usuário final.

### 🖥️ Componentes da interface:

- Título e descrição do painel  
- Três controles do tipo *switch*:
  - Sistema de trocas  
  - Notificações  
  - Modo manutenção  
- Botão de ação:
  - **Salvar configurações**
- Área de status atual:
  - Estado das funcionalidades (Ativo/Inativo)
  - Data e hora da última atualização  

---

### ⚙️ Parametrizações implementadas

Foram implementadas as seguintes parametrizações:

- Ativação/desativação do **sistema de trocas**
- Controle de envio de **notificações**
- Habilitação do **modo manutenção**

Além disso:

- Utilização de **flow context** do Node-RED para armazenamento temporário
- Estruturação dos dados em formato JSON
- Envio de dados via requisições HTTP
- Atualização automática do painel
- Feedback visual ao usuário (mensagem de sucesso)

---
Foram utilizadas APIs internas da aplicação ReUse, desenvolvidas em Next.js, seguindo o padrão REST.

A principal rota utilizada foi:

/api/admin/configuracoes

🛠️ APIs criadas

Foi desenvolvida uma API administrativa para suportar o painel.

📍 Endpoints:
GET /api/admin/configuracoes
PUT /api/admin/configuracoes

🔍 Funções das APIs
🔹 GET
Retorna as configurações atuais da plataforma
Utilizado para carregar o estado inicial do painel
🔹 PUT
Atualiza as configurações da aplicação
Recebe os dados enviados pelo Node-RED
Persiste os dados em um arquivo JSON

🔗 Integração com o painel administrativo

A integração ocorre da seguinte forma:

O usuário altera os controles no painel (switches)
Ao clicar em Salvar configurações, o Node-RED:
Monta um objeto JSON com os valores
Envia uma requisição HTTP do tipo PUT
A API Next.js:
Recebe os dados
Processa e valida
Salva no arquivo configuracoes.json
A API retorna a resposta atualizada
O Node-RED:
Atualiza o painel automaticamente
Exibe mensagem de sucesso
Atualiza o status em tempo real
🧠 Fluxo de integração
Node-RED (Dashboard)
        ↓
HTTP Request (GET / PUT)
        ↓
Next.js API (/api/admin/configuracoes)
        ↓
Arquivo JSON (persistência)
        ↓
Resposta → Atualização do painel

🚀 Resultado da integração

A integração permitiu:

✔ Persistência real das configurações
✔ Sincronização entre frontend e backend
✔ Controle dinâmico da aplicação
✔ Criação de uma camada de backoffice funcional

🏁 Conclusão

A solução implementada demonstra a eficiência da utilização de ferramentas low code (Node-RED) integradas a uma arquitetura moderna baseada em APIs (Next.js).

O sistema desenvolvido permite controle real sobre o comportamento da plataforma, garantindo:

Escalabilidade
Organização
Facilidade de manutenção

### 🔗 Link do repositório no GitHub

```text
https://github.com/1TWDOR-11/Painel-Administrativo-ReUse-Node-RED-Next.js-
