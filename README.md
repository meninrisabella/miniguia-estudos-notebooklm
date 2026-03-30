# miniguia-estudos-notebooklm
# Miniguia de Estudos: Modelos de Linguagem e Engenharia de Prompts

## Contexto e Objetivos

Este projeto tem como objetivo explorar o funcionamento dos modelos de linguagem (LLMs) e o uso de técnicas de engenharia de prompts como ferramenta de aprendizagem ativa.

A proposta foi utilizar Inteligência Artificial de forma crítica para compreender:

- Como modelos de linguagem processam texto
- O papel dos tokens e da janela de contexto
- Como prompts influenciam diretamente as respostas
- Limitações como alucinações e vieses

O objetivo final é consolidar o aprendizado em um miniguia reutilizável para estudos futuros.

---

## Fontes

As seguintes fontes foram utilizadas no NotebookLM:

1. [OpenAI Platform Docs](https://platform.openai.com/docs/introduction) — documentação oficial sobre como usar e entender os modelos da OpenAI
2. [Google ML Glossary](https://developers.google.com/machine-learning/glossary) — glossário de referência para termos de machine learning
3. [HuggingFace NLP Course](https://huggingface.co/learn/nlp-course) — curso aberto e prático sobre processamento de linguagem natural
4. [GPT-3 Paper (Brown et al., 2020)](https://arxiv.org/pdf/2005.14165.pdf) — paper técnico original do GPT-3; utilizei especificamente as seções 1 (Introduction) e 2 (Approach) para entender a arquitetura e o conceito de few-shot learning
5. [Prompting Guide](https://www.promptingguide.ai/) — guia prático e atualizado sobre técnicas de engenharia de prompts

---

## Engenharia de Prompts e "Cicatrizes"

### Prompt 1 — Tokens

**Pergunta inicial:**
> "O que são tokens em modelos de linguagem?"

**Resposta obtida (problemática):**
> "Tokens são unidades de texto usadas pelos modelos de linguagem. Eles podem representar palavras, partes de palavras ou caracteres, dependendo do tokenizador utilizado."

**Problema identificado:** A resposta era correta, mas abstrata demais. Não ficou claro o que isso significa na prática para quem está aprendendo.

**Prompt ajustado:**
> "Explique tokens de forma simples, com exemplos práticos usando frases do dia a dia."

**Resposta obtida (melhorada):**
> "A palavra 'aprendizado' pode ser dividida em tokens como ['apren', 'diz', 'ado']. A frase 'Eu gosto de IA' pode ter 5 ou 6 tokens dependendo do modelo. Isso importa porque modelos têm um limite de tokens por resposta — quanto mais tokens você usa no prompt, menos sobra para a resposta."

**Aprendizado:** Pedir exemplos concretos e cotidianos transforma uma definição técnica em algo compreensível e memorável.

---

### Prompt 2 — Janela de Contexto

**Pergunta inicial:**
> "Como funciona a janela de contexto?"

**Resposta obtida (problemática):**
> "A janela de contexto é o número máximo de tokens que o modelo pode processar simultaneamente, incluindo o prompt e a resposta gerada. Modelos mais recentes como o GPT-4 Turbo suportam até 128k tokens."

**Problema identificado:** Resposta muito técnica, cheia de números sem explicação do impacto real.

**Prompt ajustado:**
> "Explique a janela de contexto como se fosse a memória de curto prazo de uma pessoa, usando uma analogia simples."

**Resposta obtida (melhorada):**
> "Imagine que você está lendo um livro, mas só consegue lembrar das últimas 10 páginas. Tudo que veio antes simplesmente some da sua memória. A janela de contexto funciona assim: o modelo só 'enxerga' o trecho da conversa que cabe dentro desse limite. Se a conversa for longa, ele esquece o que foi dito no início."

**Aprendizado:** Analogias do cotidiano são mais eficientes do que definições técnicas quando o objetivo é compreensão, não precisão formal.

---

### Prompt 3 — Técnicas de Engenharia de Prompt

**Pergunta inicial:**
> "Como melhorar respostas de IA?"

**Resposta obtida (problemática):**
> "Para melhorar respostas de IA, você pode ajustar a temperatura, usar system prompts, aplicar técnicas de chain-of-thought e explorar few-shot learning."

**Problema identificado:** A resposta listou termos técnicos sem explicar o que cada um significa ou como aplicá-los na prática.

**Prompt ajustado:**
> "Liste as principais técnicas de engenharia de prompt com uma explicação simples e um exemplo de cada."

**Resposta obtida (melhorada):**
> "1. **Few-shot:** Dê exemplos antes de fazer a pergunta. Ex: 'Traduza: gato = cat, cachorro = dog. E cadeira?' 2. **Chain-of-thought:** Peça para o modelo pensar passo a passo. Ex: 'Resolva esse problema e explique cada etapa.' 3. **Role prompting:** Dê um papel ao modelo. Ex: 'Você é um professor de ensino médio. Explique fotossíntese.'"

**Aprendizado:** Perguntas vagas geram respostas vagas. Quanto mais específico o prompt, mais acionável a resposta.

---

### Dificuldades encontradas

- Prompts curtos e vagos resultavam em respostas genéricas e pouco úteis
- Termos técnicos sem contexto geravam respostas corretas, mas incompreensíveis para iniciantes
- Foi necessário reformular as perguntas entre 2 e 3 vezes até obter respostas realmente aproveitáveis
- Aprendi que o prompt ideal combina: **contexto + formato esperado + exemplo ou analogia**

---

## Miniguia de Estudo

### Resumo Estruturado

Modelos de linguagem são sistemas de IA que processam texto dividindo-o em **tokens** — unidades mínimas de texto — e geram respostas com base em probabilidades aprendidas durante o treinamento com bilhões de exemplos.

Esses modelos operam dentro de uma **janela de contexto** limitada, que funciona como uma memória de curto prazo: apenas o trecho visível da conversa é considerado. Quando a conversa ultrapassa esse limite, informações anteriores são "esquecidas".

A qualidade das respostas depende diretamente do **prompt**: uma instrução vaga gera uma resposta genérica; uma instrução específica, com formato e contexto definidos, gera respostas muito mais úteis.

Apesar de eficientes, esses modelos podem gerar **alucinações** — respostas incorretas apresentadas com confiança —, o que exige análise crítica de tudo que é gerado.

---

### Glossário

| Termo | Definição | Exemplo |
|---|---|---|
| **Token** | Unidade mínima de texto processada pelo modelo | "aprendizado" pode virar 3 tokens: ['apren', 'diz', 'ado'] |
| **Janela de contexto** | Limite de informação que o modelo considera por vez | Como lembrar só das últimas 10 páginas de um livro |
| **Prompt** | Instrução dada ao modelo para guiar a resposta | "Explique como se eu tivesse 10 anos" |
| **Few-shot learning** | Uso de exemplos no prompt para guiar o formato da resposta | Mostrar 2 traduções antes de pedir a terceira |
| **Chain-of-thought** | Pedir que o modelo pense passo a passo | "Resolva e explique cada etapa" |
| **Alucinação** | Resposta incorreta gerada com aparente confiança | Modelo inventa uma citação que não existe |
| **LLM** | Modelo de linguagem de grande escala treinado em enormes volumes de texto | GPT-4, Gemini, Claude |

---

### Prompts Reutilizáveis

**Para aprender conceitos:**
- `"Explique [conceito] como se eu fosse iniciante, com uma analogia do cotidiano"`
- `"Explique [conceito] em até 3 frases simples e depois dê um exemplo prático"`

**Para organizar informação:**
- `"Resuma o texto abaixo em tópicos claros, do mais importante para o menos importante"`
- `"Liste vantagens e desvantagens de [tema] em formato de tabela"`

**Para aprofundar o estudo:**
- `"Quais são as perguntas mais comuns de iniciantes sobre [tema]? Responda cada uma delas"`
- `"Me dê um quiz de 5 perguntas sobre [tema] com gabarito ao final"`

**Para revisar:**
- `"Organize os conceitos abaixo em um mapa mental em formato de texto"`
- `"Quais pontos do meu resumo estão incompletos ou imprecisos?"`

---

## Conclusão

Este projeto me mostrou que usar IA para aprender exige uma postura ativa: não basta fazer a pergunta — é preciso avaliar a resposta, identificar o que faltou e reformular. Cada prompt mal feito foi uma oportunidade de entender melhor o que eu realmente queria saber. Mais do que aprender sobre LLMs, aprendi a fazer perguntas melhores — e isso é uma habilidade que vai muito além do uso de IA.

---

*Projeto desenvolvido como parte do desafio prático da [DIO](https://www.dio.me/).*


