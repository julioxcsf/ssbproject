# 🌐 SSB BANK - Frontend

Este repositório contém a **interface web (HTML + JS)** do sistema bancário **SSB BANK**, que consome uma **API RESTful** desenvolvida com Spring Boot.  
É uma SPA (Single Page Application) simples que simula funcionalidades bancárias como:

- Cadastro e autenticação de clientes
- Visualização de contas
- Operações bancárias: depósito, saque e transferência
- Extrato de transações com filtros dinâmicos
- Alternância de status da conta (ativa/inativa)

---

## 🚀 Deploy

A interface está publicada via Netlify:

[![Netlify Status](https://api.netlify.com/api/v1/badges/342346b7-ab77-4ca4-9596-f4e2fdc3414f/deploy-status)](https://app.netlify.com/sites/swagger-ssb-api/deploys)

🌐 **Acesse aqui**: https://swagger-ssb-api.netlify.app

---

## 📁 Estrutura das Páginas

| Arquivo | Descrição |
|--------|-----------|
| `index.html` | Página inicial de login do sistema |
| `cadastrar.html` | Página para cadastro de um novo cliente |
| `cliente.html` | Painel do cliente autenticado com listagem de contas |
| `criar-conta.html` | Tela para abertura de nova conta (corrente, poupança ou investimento) |
| `conta.html` | Detalhes de uma conta específica com extrato e operações |
| `sucesso-cadastro.html` | Mensagem após cadastro de cliente bem-sucedido |
| `sucesso-conta.html` | Confirmação após criação de nova conta |
| `sucesso-operacao.html` | Tela de sucesso após operação bancária |
| `manutencao.html` | Página exibida caso o sistema esteja fora do ar (manutenção) |
| `config.js` | Arquivo de configuração contendo a URL da API backend (Render) |

---

## 🔐 Autenticação

A autenticação é baseada em **JWT**, salvo no `localStorage`.

Após o login, o token é incluído nos headers das requisições `fetch`, por exemplo:

```js
fetch(`${URL_API}/clients`, {
  headers: {
    "Authorization": `Bearer ${token}`
  }
});
