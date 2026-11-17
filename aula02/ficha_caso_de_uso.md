# Ficha do caso de uso — LLM no MVP

**Grandes Modelos de Linguagem · Residência em Engenharia de Software Inteligente (FACOM/UFMS)**
Aula 2 · Parte B · **em grupo** · entrega até **23/11/2026, 23h59** (no Moodle) · vale 20% da nota

> Copie este modelo, preencha cada seção e entregue em PDF (ou no formato indicado pelo professor). Seja objetivo: a ficha inteira cabe em 2 a 3 páginas. Ela é o ponto de partida da **oficina** (25/11): o retorno sobre a ficha acontece durante a oficina, nas visitas do professor aos grupos.

---

**Grupo:** _nome do grupo_
**Integrantes:** _nomes_
**MVP:** _nome e descrição em uma frase_

---

## 1. Funcionalidade inteligente e problema

Qual funcionalidade inteligente do MVP está em análise? Que problema do usuário ela resolve?

_Resposta:_

## 2. Situação atual: o modelo construído no bloco

O modelo desenvolvido na disciplina *Construção de Modelos de Aprendizagem de Máquina*.

| Item | Descrição |
|---|---|
| Tarefa (ex.: classificação em N classes, regressão, extração…) | |
| Dados de treino (origem, quantidade, rótulos) | |
| Métrica usada | |
| Desempenho obtido | |
| Pontos fracos observados | |

## 3. Hipótese de uso do LLM

Marque uma opção e justifique em 2 a 4 linhas.

- [ ] **Substituir** — o LLM assume a tarefa do modelo próprio.
- [ ] **Complementar** — o modelo próprio continua; o LLM acrescenta uma capacidade nova.
- [ ] **Híbrido** — cada um atua onde é melhor (ex.: o LLM só nos casos de baixa confiança).

_Justificativa:_

## 4. Entrada e saída

| | Descrição | Formato | Exemplo |
|---|---|---|---|
| **Entrada** | | (texto livre, JSON, documento…) | |
| **Saída** | | (rótulo, JSON com campos X e Y, texto…) | |

Tamanho típico da entrada, em tokens (use o notebook da Parte A): ______

## 5. Critério de sucesso

| Critério | Meta |
|---|---|
| Métrica principal e limiar (ex.: acurácia ≥ 85%, F1 da classe crítica ≥ 0,8) | |
| Latência máxima aceitável por requisição | |
| Custo máximo aceitável (por requisição ou por mês) | |
| Outros (ex.: formato da saída sempre válido) | |

## 6. Conjunto de teste

- Arquivo: `conjunto_teste.csv` (modelo em `aula02/conjunto_teste_modelo.csv`), com **20 a 30 exemplos rotulados**.
- Os mesmos exemplos serão usados para comparar o modelo próprio e o LLM.

Descreva como o conjunto foi montado (origem dos exemplos, quem rotulou, como garantiram a variedade e incluíram casos difíceis):

_Resposta:_

## 7. Restrições de dados

| Pergunta | Resposta |
|---|---|
| Os dados contêm informações pessoais ou sensíveis (LGPD)? Quais? | |
| É permitido enviar esses dados para uma API externa? | |
| É possível anonimizar ou mascarar os dados antes do envio? | |
| Há restrição de licença ou de uso comercial nos dados ou modelos? | |
| Se não for possível usar API externa, qual a alternativa (modelo local)? | |

---

### Uso de IA generativa na elaboração da ficha

Declare aqui se e como o grupo usou ferramentas de IA generativa para preparar esta ficha.

_Resposta:_
