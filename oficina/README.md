# Oficina aplicada: o LLM resolve melhor que o nosso modelo?

**Grandes Modelos de Linguagem · Residência em Engenharia de Software Inteligente (FACOM/UFMS)**\
Prof. Bruno Nogueira · **25/11/2026** · síncrona, remota · 3 h · **em grupo** · vale **20%** da nota

> **Leia o enunciado completo: [`enunciado_oficina.pdf`](enunciado_oficina.pdf).** Ele explica a ideia da oficina, lista com exemplos tudo o que o grupo precisa trazer, traz o guia passo a passo do dia, a demonstração, a entrega e os critérios de avaliação.

## Em resumo

A oficina **não é uma aula**: é uma sessão de trabalho em grupo. Cada grupo aplica ao **caso do MVP** o que fizemos na Aula 3 com a Secretaria Digital: um LLM com saída estruturada e validada, medido no **mesmo conjunto de teste** do modelo próprio, com qualidade, saídas inválidas, custo e latência, e uma **decisão provisória** (modelo próprio, LLM ou híbrido). O professor circula pelas salas dos grupos; no fim, cada grupo apresenta em 3 minutos.

| Arquivo | Para que serve |
|---|---|
| [`enunciado_oficina.pdf`](enunciado_oficina.pdf) | o enunciado completo |
| [`oficina_notebook_base.ipynb`](oficina_notebook_base.ipynb) [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bmnogueira-ufms/LLM-ESIA-2026/blob/main/oficina/oficina_notebook_base.ipynb) | o notebook-base: já roda de ponta a ponta com o exemplo da Secretaria Digital; o grupo troca pelo próprio caso |

## O que trazer pronto

- [ ] **Ficha do caso de uso e conjunto de teste** entregues no Moodle até **18/11/2026, 23h59**.
- [ ] **`conjunto_teste.csv`** (20 a 30 exemplos) com a coluna **`saida_modelo_proprio`** (a saída do modelo do grupo em cada exemplo) e, se possível, **`confianca_modelo_proprio`**.
- [ ] **Acesso ao LLM testado** antes do dia (Seção 0 do notebook-base): modelo aberto no Colab ou API com a chave nos Secrets do Colab (`LLM_API_KEY`).
- [ ] **3 a 8 exemplos para few-shot**, fora do conjunto de teste.
- [ ] **Documentos em texto**, só se o grupo for testar RAG.
- [ ] **Cópia do notebook-base** no Drive de um integrante.

## Roteiro

| Bloco | Duração aproximada | O que acontece |
|---|---|---|
| Kickoff | 15 min | objetivo, notebook-base, critérios e ordem das demonstrações |
| Sprint 1 | 75 min | o caso do grupo no notebook; prompt v1 rodando em todos os exemplos; checkpoint no chat |
| Intervalo | 10 min | |
| Sprint 2 | 50 min | novas versões do prompt, comparação com o modelo próprio, análise de erros, decisão provisória |
| Demonstração | 30 min | 3 min por grupo, na sala principal |

## Entrega (Moodle, até 23h59 de 25/11)

Atividade **"Oficina - Protótipo (entrega em grupo)"**: o link do notebook do grupo e o `.zip` gerado na última célula (registro de experimentos, resultados por versão, quadro de comparação e erros classificados).

## Avaliação (20% da nota)

| Critério | Peso |
|---|---|
| Pipeline funcionando no conjunto do grupo, com saída estruturada e validação | 30% |
| Números (métrica, inválidas, latência, custo) e comparação com o modelo próprio | 30% |
| Iteração registrada: pelo menos duas versões, com o que mudou; erros classificados | 20% |
| Demonstração: exemplo, quadro e decisão provisória, em até 3 minutos | 20% |

Detalhes e níveis de cada critério: Seção 8 do enunciado.

**Depois da oficina:** documento final até 05/12. Modelo e rubrica em [`../entrega_final/`](../entrega_final/).
