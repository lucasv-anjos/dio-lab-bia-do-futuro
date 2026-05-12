# Avaliação e Métricas

## Modo de avalição

1. **Testes estruturados:** Você define perguntas e respostas esperadas;

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: comparação poupança e tesouro selic
Pergunta do usuário:
“Sou iniciante e quero começar a investir com pouco dinheiro. O que é melhor: poupança ou Tesouro Selic?”

Possível resposta do chatbot:
“A poupança é simples e possui liquidez diária, porém normalmente rende menos que outros investimentos de baixo risco.

O Tesouro Selic é um título público emitido pelo governo brasileiro e costuma oferecer rendimento superior à poupança no longo prazo. Além disso, também possui liquidez diária, o que permite resgates rápidos.

Principais diferenças:

Poupança:
Simplicidade
Isenção de imposto de renda
Rentabilidade geralmente menor
Tesouro Selic:
Baixo risco
Rentabilidade atrelada à taxa Selic
Incidência de imposto de renda sobre os ganhos

Mesmo investimentos considerados conservadores possuem riscos, como oscilações e impacto da inflação. Para iniciantes, o Tesouro Selic costuma ser uma alternativa interessante para reserva de emergência e aprendizado.”
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 2: Usuário perguntando sobre ações
Pergunta do usuário:
“Vale a pena investir em ações da Petrobras?”

Possível resposta do chatbot:
“As ações da Petrobras podem atrair investidores devido ao pagamento de dividendos e à relevância da empresa no setor de energia.

Por outro lado, existem riscos importantes:

Oscilação do preço do petróleo
Interferência política
Volatilidade do mercado
Mudanças regulatórias

Investir em ações exige tolerância a oscilações e visão de longo prazo. Em vez de concentrar todo o capital em uma única empresa, muitos investidores preferem diversificar a carteira entre diferentes setores e ativos.”
- **Resultado:** [ ] Correto  [ ] Incorreto [x] parcial porem dentro do esperado

### Teste 3: Usuário perguntando sobre criptomoedas
Pergunta do usuário:
“Bitcoin é seguro?”

Possível resposta do chatbot:
“O Bitcoin é a criptomoeda mais conhecida do mercado e utiliza tecnologia blockchain para registrar transações de forma descentralizada.

Apesar disso, é importante entender que:

O preço pode variar muito em curtos períodos
Existe risco de perdas significativas
O mercado é altamente volátil
A segurança depende também da forma como o investidor armazena os ativos

Criptomoedas costumam ser consideradas investimentos de maior risco. Por isso, muitos investidores evitam concentrar grande parte do patrimônio nesse tipo de ativo.”
- **Resultado:** [x] Correto  [ ] Incorreto
---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- respostas sucintas sem fugir o system_prompt e sem alucinações observaveis.

**O que pode melhorar:**
- demora a resposta possivelmente vinculada a complexidade do gpt-oss, verificar a possibilidade de rodar o aplicativo em uma maquina dedicada para melhor desempenho
- no código é explicitado para que utilize apenas 20 exemplos do dataset para melhor desempenho operacional, possivel aumentar o volume de informações sem precisar comprometer tanto o desempenho criando funções de pesquisa e filtro de informações porem exigiria maior complexidade
