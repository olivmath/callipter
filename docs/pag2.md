# Página 2: Proof of Concept (PoC)

A Proof of Concept (PoC) da plataforma **Callipter** tem como objetivo demonstrar as funcionalidades chave para a tokenização de games, com foco nas atividades essenciais que geram maior impacto. Aqui, buscamos executar os 1% de trabalho que entregam 50% dos resultados.

## **1. Frontend (Portal do Usuário)**

O frontend é a interface onde os usuários poderão gerenciar universos, assets e realizar outras operações essenciais.

### **Funcionalidades**

- **Tela de Cadastro/Login**:

  - Permite que os usuários se cadastrem e façam login na plataforma.

- **Tela de CRUD de Universo**:

  - **Nome do Universo**: Definir o nome do universo.
  - **Descrição**: Descrever o universo.
  - **Ações**: Criar, Editar ou Apagar universos.
  - **Restrição**: Universos criados não podem ser editados após a criação.

- **Tela de CRUD de Assets de um Universo**:
  - **Tipos de Assets**: NFT, Non-NFT.
  - **Configurações de Assets**:
    - Nome, Descrição e Quantidade.
    - Moeda: Nome, Símbolo e Quantidade.
    - Opções de Adicionar, Remover ou Editar assets.

### **Tecnologia para o Frontend**:

- **Framework**: React com TypeScript.
- **Comunicação com o Backend**: Axios para chamadas REST/GraphQL.
- **Biblioteca para UI**: Material-UI.

---

## **2. Backend (API Rest/GraphQL)**

A API backend será responsável por gerenciar todas as operações envolvendo universos, assets, autenticação e transações.

### **EndPoints**

- **API de Login**:

  - **Cadastro**: Endpoint para criar um novo usuário.
  - **Login**: Endpoint para autenticação do usuário.

- **API CRUD de Universo**:

  - **Configura Universo**: Endpoint para configurar o universo.
  - **Editar Universo**: Modifica as propriedades do universo.
  - **Apagar Universo**: Remove um universo.
  - **Criar Universo**: Endpoint para criar um novo universo.

- **API CRUD de Assets**:

  - **Adicionar Asset**: Endpoint para adicionar novos assets a um universo.
  - **Editar Asset**: Modificar um asset existente.
  - **Apagar Asset**: Remover um asset de um universo.
  - **Criar Asset**: Endpoint para criar novos assets.

- **API de Listagem de Universos**:

  - **Endpoint de Listagem**: `GET /universos` para listar todos os universos criados por um usuário.

- **API de Autenticação**:

  - **Geração de API Key**: `POST /auth/generate-api-key` para gerar uma chave de API para acessar os universos.

- **API de Transações**:
  - **Transações de Tokens**: `POST /universos/{id}/transacoes` para realizar transações dentro de um universo.

### **Tecnologia para o Backend**:

- **Framework**: NestJS com GraphQL.
- **Banco de Dados**: PostgreSQL para gerenciamento de dados dos universos e assets.
- **Multi-Tenancy**: Utilização de schemas separados no banco de dados para isolar dados de diferentes universos.

## **3. SDK (C# para o Jogo)**

O SDK em C# será uma biblioteca simples para integrar os universos e assets diretamente no jogo.

### **Funções Principais**:

- **Função de Conexão com a API**:

  - O SDK se conecta ao backend utilizando a API Key para acessar os dados do universo.

- **Função de Interação com Assets**:

  - Permite que o jogo acesse skins, armas e moedas do universo e interaja com esses itens.

- **Função de Transações de Tokens**:
  - O SDK permite que o jogador faça transações de tokens diretamente dentro do jogo.

### **Tecnologia para o SDK**:

- **Linguagem**: C#.
- **Pacote de Comunicação HTTP**: HttpClient para fazer chamadas REST/GraphQL.

## **4. Infraestrutura DevOps**

A infraestrutura para a PoC envolverá containers e orquestração para garantir a escalabilidade e a integração com a blockchain.

### **Componentes**:

- **Container Orbit L3 Arbitrum**: Blockchain utilizada para registrar e gerenciar transações de tokens.
- **Container Indexador (TheGraph)**: Usado para cache e indexação da blockchain.
- **Container de Smart Contracts**: Para fazer o deploy dos contratos inteligentes e dados dos assets dentro do universo.

---

## **Fluxo de Operações da PoC**

1. **Criação de Universo**:

   - O usuário acessa o frontend, faz login e cria um novo universo.
   - O usuário adiciona assets (skins, armas, moedas) e configura suas propriedades (raridade, variação).
   - O frontend faz uma chamada à API para criar o universo e registrar os assets.

2. **Processamento no Backend**:

   - O backend recebe o request, cria um novo schema no banco de dados e inicia o processo de deploy dos containers para o novo universo.

3. **Geração da API Key**:

   - O sistema gera uma chave de API exclusiva para o universo e a envia ao frontend, para que o SDK do jogo a utilize.

4. **Integração com o Jogo**:

   - O SDK se conecta ao backend com a API Key para acessar os dados do universo.
   - O jogador interage com os assets no jogo, podendo comprar, vender ou utilizar itens tokenizados.

5. **Tokenização e Transações**:
   - Sempre que o jogador realiza uma transação (compra/venda de assets), o SDK chama o backend para registrar a transação de token, que é refletida na blockchain.
   - O usuário pode adicionar novos assets, mas não pode removê-los, podendo apenas criar novos universos.
