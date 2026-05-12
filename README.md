# 🤖 BIA — Assistente de Investimentos com IA Generativa

> Projeto desenvolvido como parte do desafio **DIO Lab: BIA do Futuro** — Digital Innovation One  
> Fork de [digitalinnovationone/dio-lab-bia-do-futuro](https://github.com/digitalinnovationone/dio-lab-bia-do-futuro)

---

## 📌 Sobre o Projeto

A **BIA (Base de Investimentos com IA)** é um agente financeiro inteligente voltado para **investidores iniciantes** que se sentem perdidos no excesso de informações — muitas delas de procedência duvidosa — sobre o mercado financeiro.

O agente não faz recomendações de investimentos. Em vez disso, atua como um **professor particular**: apresenta riscos, contextualiza produtos financeiros e auxilia na tomada de decisão com base em dados pré-estabelecidos, sempre de forma acessível e didática.

---

## 🎯 Caso de Uso

| | |
|---|---|
| **Problema** | Excesso de conteúdo financeiro não confiável que confunde investidores iniciantes |
| **Solução** | Agente que analisa dados mockados do perfil do usuário e oferece contexto educacional sobre investimentos |
| **Público-alvo** | Investidores iniciantes que buscam orientação sem receber recomendações diretas |

---

## 🧠 Persona do Agente

- **Nome:** AI (Assistente de Investimentos)
- **Tom:** Informal, acessível e didático — como um professor particular
- **Comportamento:**
  - Comunicação clara e sem jargões desnecessários
  - Utiliza simulações para ilustrar cenários
  - Apresenta riscos, sem fazer recomendações de investimento
  - Inclui a fonte das informações nas respostas

**O que o agente NÃO faz:**
- Não recomenda investimentos específicos
- Não acessa dados bancários sensíveis
- Não substitui um profissional certificado (CFA, CFP, etc.)

---

## 🏗️ Arquitetura

```
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface Streamlit]
    B --> C[LLM - Ollama local]
    C --> D[Base de Conhecimento - JSON/CSV]
    D --> C
    C --> E[Validação Anti-Alucinação]
    E --> F[Resposta ao Usuário]
```

| Componente | Tecnologia |
|---|---|
| Interface | [Streamlit](https://streamlit.io/) |
| LLM | [Ollama](https://ollama.ai/) (execução local) |
| Base de Conhecimento | Arquivos JSON e CSV mockados |
| Linguagem | Python 3 |

---

## 📁 Estrutura do Repositório

```
📁 dio-lab-bia-do-futuro/
│
├── 📄 README.md
│
├── 📁 docs/                           # Documentação do projeto
│   ├── 01-documentacao-agente.md      # Caso de uso, persona e arquitetura
│   ├── 02-base-conhecimento.md        # Estratégia de dados
│   ├── 03-prompts.md                  # Engenharia de prompts e system prompt
│   ├── 04-metricas.md                 # Métricas de avaliação
│   └── 05-pitch.md                    # Roteiro do pitch (3 min)
│
├── 📁 src/                            # Código da aplicação
│   └── app.py                         # Aplicação Streamlit
│
└── 📁 data/                           # Dados mockados para o agente
    ├── transacoes.csv                  # Histórico de transações do cliente
    ├── historico_atendimento.csv       # Histórico de atendimentos anteriores
    ├── perfil_investidor.json          # Perfil e preferências do investidor
    └── produtos_financeiros.json       # Produtos e serviços disponíveis
```

---

## 🚀 Como Executar

### Pré-requisitos

- Python 3.9+
- [Ollama](https://ollama.ai/) instalado e rodando localmente
- Dependências Python (instalar via pip)

### Instalação

```bash
# Clone o repositório
git clone https://github.com/lucasv-anjos/dio-lab-bia-do-futuro.git
cd dio-lab-bia-do-futuro

# Instale as dependências
pip install -r requirements.txt

# Certifique-se de que o Ollama está rodando
ollama serve

# Inicie a aplicação
streamlit run src/app.py
```

---

## 🔒 Segurança e Anti-Alucinação

Como o setor financeiro exige confiabilidade, o agente foi projetado com as seguintes salvaguardas:

- As respostas incluem a fonte da informação utilizada
- O agente responde apenas com base nos dados fornecidos na base de conhecimento
- Situações fora do escopo são reconhecidas e redirecionadas

---

## 📊 Métricas de Avaliação

O agente é avaliado com base em:

- **Precisão das respostas** — alinhamento com os dados da base de conhecimento
- **Taxa de respostas seguras** — ausência de alucinações ou informações inventadas
- **Coerência com o perfil** — adequação da resposta ao perfil do investidor simulado

Detalhes em [`docs/04-metricas.md`](docs/04-metricas.md).

---

## 🛠️ Ferramentas Utilizadas

| Categoria | Ferramenta |
|---|---|
| LLM local | [Ollama](https://ollama.ai/) |
| Interface | [Streamlit](https://streamlit.io/) |
| Diagramas | [Mermaid](https://mermaid.js.org/) |
| Orquestração (sugestão) | [LangChain](https://www.langchain.com/) / [LangFlow](https://www.langflow.org/) |

---

## 📄 Documentação

| Arquivo | Conteúdo |
|---|---|
| [`docs/01-documentacao-agente.md`](docs/01-documentacao-agente.md) | Caso de uso, persona, arquitetura e segurança |
| [`docs/02-base-conhecimento.md`](docs/02-base-conhecimento.md) | Estratégia e estrutura dos dados |
| [`docs/03-prompts.md`](docs/03-prompts.md) | System prompt, exemplos de interação e edge cases |
| [`docs/04-metricas.md`](docs/04-metricas.md) | Métricas e critérios de avaliação |
| [`docs/05-pitch.md`](docs/05-pitch.md) | Roteiro do pitch de 3 minutos |

---

## 👤 Autor

**Lucas V. Anjos**  
Projeto desenvolvido para o Bootcamp DIO — [digitalinnovationone](https://github.com/digitalinnovationone)

---

## 📜 Licença

Este repositório é um fork educacional. Consulte o repositório original para informações de licença.
