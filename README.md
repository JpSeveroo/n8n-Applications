# 🧩 n8n Applications

Repositório para armazenamento, versionamento e documentação de **workflows criados no n8n**.  
Aqui são mantidas automações desenvolvidas localmente, bem como exemplos e testes de integração com outras plataformas (GitHub, Telegram, APIs e mais).

---

## 🚀 Sobre o projeto

Este repositório tem como objetivo:
- 📦 Centralizar workflows exportados do **n8n**;
- 🧠 Servir como base para estudo e desenvolvimento de automações;
- 🔄 Permitir versionamento e compartilhamento de fluxos criados localmente;
- ⚙️ Explorar integrações com serviços externos (ex: GitHub, APIs, Webhooks, Bots, etc).

Os workflows aqui podem ser executados em uma instância local do n8n ou importados em qualquer servidor remoto configurado.

---

## 🧰 Estrutura do Repositório
- n8n-applications/
- │
- ├── n8n_workflows/ → Workflows exportados em formato .json
- │ ├── exemplo_webhook.json
- │ ├── automacao_github.json
- │ └── ...
- │
- ├── scripts/ → Scripts auxiliares (ex: automação de exportação e push)
- │ └── auto_commit.sh
- │
- ├── README.md → Documentação principal
- └── .gitignore


---

## ⚙️ Como usar

### 1. Instale o n8n localmente
Siga a documentação oficial:  
👉 [https://docs.n8n.io/getting-started/installation/](https://docs.n8n.io/getting-started/installation/)

### 2. Importe um workflow
1. Baixe qualquer arquivo `.json` da pasta `n8n_workflows/`;
2. No painel do n8n, clique em **“Import → From File”**;
3. Selecione o arquivo e clique em **Importar**.

### 3. Execute o fluxo
Após importar, clique em **“Execute Workflow”** para testar localmente.

---

## 🔄 Automação de versionamento (opcional)

Caso deseje atualizar automaticamente os workflows no GitHub sempre que modificar um, use o comando:

```bash
n8n export:workflow --id=<ID_DO_WORKFLOW> --output=./n8n_workflows/<nome>.json
git add .
git commit -m "Atualiza workflow <nome>"
git push

```

💡 É possível automatizar esse processo dentro do próprio n8n com o nó Execute Command.

---

## 🌐 Integrações testadas

- ✅ GitHub (via Webhooks)
- ✅ Telegram Bot
- ✅ APIs REST e JSON
- ✅ Google Sheets
- ✅ Discord

(a lista será atualizada conforme novas automações forem criadas)

---

## 📜 Licença

Este repositório está sob a licença MIT.
Sinta-se livre para usar, modificar e distribuir os workflows conforme desejar.

---

## 🧑‍💻 Autor

João Pedro
Desenvolvedor e entusiasta de automações com n8n.
📫 Contato: severojoaoopedro90@gmail.com
