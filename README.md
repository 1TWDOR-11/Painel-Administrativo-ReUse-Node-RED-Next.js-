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

### 🔗 Link do repositório no GitHub

```text
https://github.com/1TWDOR-11/Painel-Administrativo-ReUse-Node-RED-Next.js-
