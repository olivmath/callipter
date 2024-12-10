# **Página 3: Milestones**

## **Frontend (4 semanas)**

1. **Cadastro e Login (Semana 1)**

   - **Criação da tela de cadastro de usuários.**
   - **Criação da tela de login de usuários.**
   - **Validação de entrada de dados e autenticação no backend.**

2. **Configuração de Universos (Semana 2)**

   - **Tela para criar novos universos.**
   - **Tela para editar/atualizar informações do universo.**
   - **Validação e salvamento de dados no backend.**

3. **Lançamento de Universos (Semana 3)**
   - **Tela para visualizar e lançar universos já configurados.**
   - **Integração com o backend para chamada de criação de universos.**

---

## **Backend (6 semanas)**

### **Setup-Game**

1. **Autenticação de Usuários (Semana 1)**

   - **Endpoint para cadastro de usuários.**
   - **Endpoint para login e verificação de credenciais.**
   - **Gerenciamento de sessões ou tokens JWT.**

2. **CRUD de Usuários (Semana 2)**

   - **API para criar, editar, listar e deletar usuários.**
   - **Implementação de controle de acesso.**

3. **CRUD de Universos (Semana 3)**
   - **API para criar, editar, listar e deletar universos.**
   - **Lógica de negócios para criação de novos universos e seus respectivos assets.**

---

### **Run-Game**

1. **Autenticação com API Key (Semana 4)**

   - **Validação da API Key para cada universo.**

2. **Leitura nos Universos (Semana 5)**

   - **API para ler dados dos universos (GraphQL).**

3. **Escrita nos Universos (Semana 6)**

   - **API para escrever dados nos universos vindos do SDK.**

---

## **Infraestrutura (3 semanas)**

1. **Subir os Universos (Semana 1)**

   - **Módulo no backend para subir containers automaticamente com os componentes necessários (blockchain, smart contracts, assets).**
   - **Gerenciar a criação e destruição dos ambientes dos universos.**

2. **Integração com Kubernetes/Docker (Semana 5)**

   - **Configuração do ambiente de containers com Kubernetes ou Docker.**

3. **Testes com Kubernetes/Docker (Semana 6)**
   - **Validação do fluxo completo da infra.**

---

## **SDK (4 semanas)**

1. **Criar Space Invaders (versão simples) (Semana 1)**

   - **Desenvolver uma versão simplificada do jogo Space Invaders no Unity, usando C#.**
   - **Implementação básica de movimento, disparo, colisões, pontos e skins.**

2. **Adicionar SDK (Semana 2)**

   - **Desenvolver o SDK que conecta o jogo (Space Invaders) ao backend para interagir com os universos.**
   - **Integrar o SDK com a API de universos para leitura e escrita de dados (ex.: interagir com assets, realizar transações de tokens).**

3. **Tokenizar o Jogo (Semana 3)**

   - **Implementar a tokenização de assets no jogo (skins e moedas) através do backend.**

4. **Testes no Jogo (Semana 4)**

   - **Validar fluxo de tokenização dos assets, compras, vendas ou trocados no mesmo universo.**

---

## **Resumo de Prazos para 1 pessoas:**

- **Frontend:** 4 semanas
- **Backend:** 6 semanas
- **Infraestrutura:** 3 semanas
- **SDK + Game:** 4 semanas
