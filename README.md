# 🚀 Subindo o N8N com Docker em 5 Minutos

Este repositório acompanha o vídeo publicado no canal da [Data Driven School](https://www.youtube.com/@datadrivenschool), onde mostramos como subir o N8N em um container Docker com persistência de dados local.

📺 **Assista ao vídeo completo aqui:**  
👉 [Do Zero ao Workflow: Subindo N8N com Docker em 5 Minutos](https://www.youtube.com/watch?v=LINK_DO_VIDEO)

---

## ✅ Pré-requisitos

- Docker instalado  
- Docker Compose instalado  
- Git (opcional)

---

## 📁 Estrutura do Projeto

```
📦 n8n-docker

 ┣ 📄 docker-compose.yml
 ┗ 📄 README.md
```

---

## ⚙️ Passo a Passo para Subir o N8N

### 1. Clone o Repositório

```bash
git clone https://github.com/datadrivenschool/n8n-docker.git
cd n8n-docker
```

### 2. Dê Permissões à Pasta `n8n_data`

```bash
mkdir -p ./n8n_data
sudo chown -R 1000:1000 ./n8n_data
```

> ⚠️ Isso garante que o container do N8N (que roda como usuário 1000) consiga escrever os dados no volume local.

### 3. Suba o Container

```bash
docker-compose up -d
```

### 4. Acesse o N8N no Navegador

Abra: [http://localhost:5678](http://localhost:5678)

---

## 🧠 O que é o N8N?

O **n8n** (pronuncia-se *n-eight-n*) é uma plataforma open-source para **automatizar processos** e integrar APIs sem escrever código manualmente. Ideal para:

- Workflows de dados
- Notificações automáticas
- ETL simples
- Integrações entre sistemas

---

## 📦 docker-compose.yml

```yaml
version: "3.8"

services:
  n8n:
    image: n8nio/n8n
    restart: always
    ports:
      - "5678:5678"
    volumes:
      - ./n8n_data:/home/node/.n8n
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=admin123
```

> ⚠️ Altere as variáveis `N8N_BASIC_AUTH_USER` e `N8N_BASIC_AUTH_PASSWORD` para garantir segurança mínima.

---

## 📚 Conheça a Data Driven School

🔥 Quer evoluir em Ciência de Dados, Engenharia ou Machine Learning?  
👉 Acesse: [https://www.datadrivenschool.com](https://www.datadrivenschool.com)

---

## ✉️ Dúvidas?

Abra uma **issue** aqui no repositório ou comente no vídeo no YouTube.

---

