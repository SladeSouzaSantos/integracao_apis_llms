# INTEGRACAO_APIS_LLMS 🚀

Este repositório atua como um ecossistema de serviços para integração e orquestração de múltiplas APIs de Large Language Models (LLMs). O objetivo é centralizar a lógica de roteamento, filtragem e padronização de chamadas entre diferentes provedores.

## 📂 Estrutura do Repositório

O repositório está organizado em subprojetos independentes. Atualmente, contamos com:

### 1. [Smart Model Router Gateway](./smart-model-router-gateway) 🛡️
**Status:** `Ativo`

O **Smart Model Router Gateway** é um gateway inteligente que atua como um intermediário entre sua aplicação e a [OpenRouter](https://openrouter.ai/). Ele permite selecionar automaticamente o modelo ideal com base em métricas de performance ou custo, evitando que você precise gerenciar múltiplos endpoints manualmente.

#### ✨ Funcionalidades
- **Roteamento Inteligente:** Seleção de modelos baseada em `throughput`, `latency` ou `price`.
- **Configuração Dinâmica:** Controle total de temperatura, tokens máximos e prompts de sistema via `config.ts`.
- **Fallback Automático:** Garantia de disponibilidade utilizando a lista de modelos pré-configurados.
- **Abstração de Provedor:** Interface única para múltiplos modelos da OpenRouter.

#### ⚙️ Configuração e Instalação

1. **Pré-requisitos**
   - Node.js (v20 ou superior recomendada)
   - Gerenciador de pacotes (npm ou yarn)

2. **Instalação**
   ```bash
   cd smart-model-router-gateway
   npm install
   ```

3. **Variáveis de Ambiente**
   Crie um arquivo `.env` na pasta do projeto e adicione sua chave da OpenRouter:
   ```env
   OPENROUTER_API_KEY=sua_chave_aqui
   ```

4. **Execução**
   Para ambiente de desenvolvimento:
   ```bash
   npm run dev
   ```

#### 🚀 Exemplo de Uso (Via cURL)
```bash
curl -X POST http://localhost:3000/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "messages": [{"role": "user", "content": "Olá, quem é você?"}]
  }'
```

---

### 2. [Langchain Intro](./langchain-intro) 🧠
**Status:** `Ativo`

Este projeto serve como um laboratório prático para exploração e validação de implementações utilizando os frameworks **LangChain** e **LangGraph**. O foco é o estudo de fluxos de agentes, memória e orquestração de cadeias complexas.

#### ✨ Funcionalidades
- **Estudo de Frameworks:** Implementação prática de conceitos do LangChain e LangGraph.
- **Validação de Fluxos:** Verificação de grafos de estados e agentes autônomos.
- **Ambiente de Testes:** Suite de testes E2E para garantir a integridade dos fluxos.

#### ⚙️ Configuração e Instalação

1. **Pré-requisitos**
   - Node.js (v20 ou superior)
   - Gerenciador de pacotes (npm ou yarn)

2. **Instalação**
   ```bash
   cd langchain-intro
   npm install
   ```

3. **Variáveis de Ambiente**
   Crie um arquivo `.env` na pasta do projeto:
   ```env
   LANGSMITH_API_KEY=your-api-key
   LANGCHAIN_TRACING_V2=true
   LANGCHAIN_PROJECT=langchain-intro
   ```

4. **Execução e Testes**
   Para rodar os testes de integração/E2E:
   ```bash
   npm test
   ```

#### 🚀 Exemplo de Uso
```bash
curl localhost:3000/chat --data '{"question": "uppercase this"}' -H "Content-type: application/json"
```

---

### 3. [Medical Appointment](./medical-appointment) 🩺
**Status:** `Ativo`

O **Medical Appointment** é um serviço especializado voltado para o gerenciamento e automação de agendamentos médicos utilizando IA. O projeto utiliza agentes inteligentes para processar requisições, verificar disponibilidade e estruturar dados de consultas médicas de forma automatizada.

#### ✨ Funcionalidades
- **[Funcionalidade 1: Ex: Extração de Entidades]:** [Ex: Identificação automática de especialidade e data da consulta via NLP].
- **[Funcionalidade 2: Ex: Orquestração de Agentes]:** [Ex: Uso de LangGraph para gerenciar o fluxo entre paciente e médico].
- **[Funcionalidade 3: Ex: Validação de Dados]:** [Ex: Verificação de formatos de data e integridade de informações médicas].

#### ⚙️ Configuração e Instalação

1. **Pré-requisitos**
   - Node.js (v20 ou superior)
   - Gerenciador de pacotes (npm ou yarn)

2. **Instalação**
   ```bash
   cd medical-appointment
   npm install
   ```

3. **Variáveis de Ambiente**
   Crie um arquivo `.env` na pasta do projeto com as configurações necessárias:
   ```env
   # [Exemplo: API Key para o serviço de IA]
   [NOME_DA_VARIAVEL]=[sua_chave_aqui]
   
   # [Exemplo: Configuração de Banco de Dados ou outro serviço]
   [OUTRA_VARIAVEL]=[valor]
   ```

4. **Execução e Testes**
   Para rodar os testes de integração/E2E:
   ```bash
   npm test
   ```

#### 🚀 Exemplo de Uso
```bash
curl -X POST http://localhost:3000/appointment \
  -H "Content-Type: application/json" \
  -d '{
    "patient_name": "João Silva",
    "specialty": "Cardiologia",
    "date": "2024-12-25"
  }'
```

---

## 🛠️ Roadmap de Projetos
- [x] Smart Model Router Gateway
- [x] Langchain Intro
- [x] Medical Appointment
- [ ] Song Highlights
- [ ] Safeguard Prompt Injection
- [ ] RAG Neo4j Students
- [ ] Doc Analysis

## 📜 Licença
Este projeto está sob a licença ISC.