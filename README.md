# DevOps Lab: Node.js com CI/CD no Azure

Este projeto é um laboratório prático de implementação de um pipeline completo de DevOps (CI/CD) utilizando contêineres.

## 🚀 Tecnologias Utilizadas
- **Node.js & Express:** Aplicação Web simples.
- **Docker:** Containerização da aplicação.
- **GitHub Actions:** Automação de Build e Testes (CI).
- **Docker Hub:** Registro de imagens de contêiner.
- **Azure Web App (Linux):** Hospedagem da aplicação.
- **Webhooks:** Gatilho para Deploy Contínuo (CD).

## ⚙️ Arquitetura do Pipeline

1. **CI (Integração Contínua):**
   - A cada `push` na branch `main`, o GitHub Actions é acionado.
   - O workflow instala dependências e roda os testes unitários.
   - Se aprovado, constrói a imagem Docker e envia para o Docker Hub.

2. **CD (Entrega Contínua):**
   - O Docker Hub dispara um Webhook para o Azure.
   - O Azure Web App baixa a nova imagem (`latest`) e reinicia o contêiner automaticamente.

## 🛠️ Como rodar localmente

1.  Clone o repositório:
    ```bash
    git clone [https://github.com/SEU-USUARIO/NodeJs-Express.git](https://github.com/SEU-USUARIO/NodeJs-Express.git)
    cd NodeJs-Express
    ```

2.  Construa a imagem Docker:
    ```bash
    docker build -t meu-app-node .
    ```

3.  Execute o contêiner:
    ```bash
    docker run -p 3000:3000 meu-app-node
    ```

4.  Acesse a aplicação no navegador:
    [http://localhost:3000](http://localhost:3000)