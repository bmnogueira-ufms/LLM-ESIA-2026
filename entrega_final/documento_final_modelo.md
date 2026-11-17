# Documento final: LLM no MVP

**Grandes Modelos de Linguagem · Residência em Engenharia de Software Inteligente (FACOM/UFMS)**\
Entrega em grupo · documento + anexos + vídeo de até 5 minutos · até **05/12/2026, 23h59** · vale 60% da nota

> Copie este modelo, substitua os textos em itálico e apague as instruções (os blocos que começam com ">"). O corpo do documento tem **até 6 páginas**, sem contar capa e anexos. Entregue em PDF, junto com o `.zip` dos anexos e o link do **vídeo explicativo de até 5 minutos** (roteiro no `enunciado_entrega_final.pdf`).

---

**Grupo:** _nome do grupo_\
**Integrantes:** _nomes_\
**MVP:** _nome e descrição em uma frase_\
**Funcionalidade inteligente analisada:** _uma frase_\
**Notebook (link com acesso de leitura):** _link_\
**Vídeo explicativo (até 5 min, link aberto):** _link_

---

## 1. Resumo da decisão

> 4 a 6 linhas. Qual abordagem o grupo escolheu (modelo próprio, LLM ou híbrido) e qual é a principal evidência? Quem ler só esta seção precisa saber a decisão e o número que a sustenta.

_Exemplo de forma: "Escolhemos uma solução híbrida: o classificador próprio responde quando a confiança é ≥ 0,7 (75% dos casos) e um LLM few-shot decide os demais. No conjunto de teste (30 exemplos), o híbrido acertou 90%, contra 83% do modelo próprio e 87% do LLM sozinho, com latência p95 de 0,9 s e custo projetado de US$ 4/mês, dentro das metas da ficha."_

## 2. Contexto e critério de sucesso

> Qual problema do usuário a funcionalidade resolve? Qual é a entrada e qual é a saída? Repita o critério de sucesso definido na ficha. Se ele mudou depois da entrega da ficha (por exemplo, com o retorno da oficina), diga o que mudou e por quê.

| | Descrição |
|---|---|
| Entrada (formato, tamanho típico em tokens) | |
| Saída (formato, valores possíveis) | |

| Critério | Meta definida na ficha |
|---|---|
| Métrica principal e limiar | |
| Latência máxima (p95) | |
| Custo máximo (por mês, no volume esperado de ___ chamadas) | |
| Outros (ex.: saída sempre válida) | |

## 3. Protocolo de comparação

> Descreva o suficiente para que outra pessoa repita a comparação.

**Conjunto de teste:** _quantos exemplos, origem, quem rotulou, distribuição das classes ou casos, quantos difíceis. Confirme que nenhum exemplo foi usado no treino do modelo próprio nem nos exemplos few-shot._

**Modelo próprio:** _tipo de modelo, dados de treino (quantidade), onde roda._

**LLM:**

| Item | Valor |
|---|---|
| Modelo e versão exata | |
| Onde roda (API do provedor, agregador, Colab, Ollama…) | |
| Parâmetros (temperatura, max_tokens…) | |
| Técnicas (zero-shot, few-shot, CoT, saída estruturada, RAG) | |

**Versões de prompt testadas** (do `registro_experimentos.csv`):

| Versão | O que mudou em relação à anterior | Métrica principal | Inválidas |
|---|---|---|---|
| v1 | | | |
| v2 | | | |

**Métricas:** _quais e por quê; como as saídas inválidas foram contadas (como erro); como latência e custo foram medidos._

## 4. Resultados

> O quadro principal do documento. Mesmo conjunto de teste para todas as linhas. Marque o que atingiu a meta.

| Abordagem | Métrica principal | Outra métrica (ex.: F1 macro) | Inválidas | Latência p50 / p95 | Custo por mês | Dados rotulados usados | Atinge as metas? |
|---|---|---|---|---|---|---|---|
| Modelo próprio | | | - | | | | |
| LLM: melhor versão | | | | | | | |
| Híbrido (se houver) | | | | | | | |

_Interpretação: o que os números mostram e o que eles não permitem concluir. Lembre que, com 20 a 30 exemplos, um acerto vale de 3 a 5 pontos percentuais._

## 5. Pipeline de integração

> Como a solução escolhida funciona dentro do MVP. Um diagrama simples ajuda. Se a decisão for o modelo próprio, descreva o pipeline do LLM que foi avaliado e explique por que ele não foi adotado.

- **Fluxo:** _entrada → (pré-processamento, mascaramento de dados) → chamada → parsing e validação → repetição → fallback → uso no MVP._
- **Esquema da saída:** _campos, tipos e valores permitidos._
- **Tratamento de falhas:** _o que acontece quando a saída é inválida, quando a API cai ou demora (tempo limite)._
- **RAG (se houver):** _documentos, chunking (tamanho e sobreposição), modelo de embeddings, índice, k._
- **Operação:** _onde a chamada acontece (síncrona ou em fila), onde ficam as chaves, o que é registrado em log, como trocar de modelo._

O prompt final completo está no **Anexo A**.

## 6. Exemplos e análise de erros

> Pelo menos 3 acertos e 3 erros representativos. Para os erros, use a classificação da oficina.

| # | Entrada | Esperado | Modelo próprio | LLM | Comentário |
|---|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |
| 6 | | | | | |

| Tipo de erro | Modelo próprio | LLM |
|---|---|---|
| caso ambíguo | | |
| rótulo do teste errado | | |
| fora do formato | | |
| faltou contexto | | |
| alucinação | | |
| erro grosseiro | | |

_O que os erros ensinam: as abordagens erram nos mesmos casos? O que mudaria no prompt, nos dados ou no modelo?_

## 7. Limitações e riscos

> Cada linha com evidência (como foi observado ou testado) e mitigação concreta. Inclua os riscos que fizerem sentido para o seu caso.

| Risco | Evidência (como observamos ou testamos) | Mitigação adotada ou proposta |
|---|---|---|
| Alucinação | | |
| Saída inválida | | |
| Prompt injection | | |
| Viés | | |
| Dados pessoais (LGPD) | | |
| Custo e latência | | |
| Dependência do provedor (mudança ou retirada do modelo) | | |

## 8. Decisão final e próximos passos

- **Decisão:** _modelo próprio, LLM ou híbrido, em uma frase._
- **O que mudaria a decisão:** _ex.: volume mensal acima de X, novos dados rotulados, mudança de preço, restrição de dados._
- **Trabalho futuro:** _ex.: fine-tuning leve com N exemplos, mais dados de teste, RAG com documentos oficiais._

---

### Declaração de uso de IA generativa

_Declare se e como o grupo usou ferramentas de IA generativa na preparação deste documento, do código e do vídeo._

---

## Anexos

- **Anexo A: Prompt final completo** (mensagem de sistema, exemplos few-shot e formato), com o nome e a versão do modelo.
- **Anexo B: `registro_experimentos.csv`** (no `.zip`).
- **Anexo C: `resultados_<versao>.csv`** da versão escolhida (no `.zip`).
- **Anexo D: `erros_<versao>.csv`** com a coluna `tipo_erro` preenchida (no `.zip`).
