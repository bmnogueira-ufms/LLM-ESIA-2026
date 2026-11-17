# Documento final: definição, modelo e rubrica

**Grandes Modelos de Linguagem · Residência em Engenharia de Software Inteligente (FACOM/UFMS)**\
Prof. Bruno Nogueira · **em grupo** · entrega até **05/12/2026, 23h59** · vale **60%** da nota

---

## O que é

Um documento **curto** em que o grupo responde, com evidências, à pergunta que guia a disciplina:

> **Para a funcionalidade inteligente do MVP, usar o modelo próprio, um LLM ou uma solução híbrida?**

O documento fecha o caminho da disciplina (ficha do caso de uso → protótipo e números na oficina → **decisão justificada**).

A disciplina **não exige** que o LLM vença. "O nosso modelo próprio é melhor, e estes números mostram isso" é uma conclusão válida. O que vale nota é a **qualidade da decisão**: comparação justa, números, análise crítica e um pipeline que outra pessoa conseguiria reproduzir.

---

## Formato e entrega

| Item | Definição |
|---|---|
| Tamanho | **até 6 páginas** no corpo do texto (sem contar capa e anexos) |
| Formato | **PDF**, fonte 11 ou maior; use o modelo [`documento_final_modelo.md`](documento_final_modelo.md) (ou o [`.docx`](documento_final_modelo.docx)) |
| Anexos obrigatórios | prompt final completo · `registro_experimentos.csv` · resultados por exemplo (`resultados_<versao>.csv`) · erros classificados (`erros_<versao>.csv`) |
| Reprodutibilidade | link do notebook (Colab com leitura para quem tiver o link, ou repositório) |
| Onde entregar | Moodle, atividade **"Documento final (entrega em grupo)"**: o PDF + um `.zip` com os anexos em CSV |
| Quem entrega | uma pessoa do grupo |
| Prazo | **05/12/2026, 23h59** (horário de MS) |

Os anexos são os arquivos que o notebook-base da oficina já gera em `resultados_oficina/`. Se o grupo rodou novas versões depois da oficina, entregue o registro atualizado.

---

## Estrutura do documento

| Seção | Conteúdo | Tamanho sugerido |
|---|---|---|
| **Cabeçalho** | grupo, integrantes, MVP em uma frase, link do notebook | - |
| **1. Resumo da decisão** | a abordagem escolhida e o principal número que a sustenta | 4 a 6 linhas |
| **2. Contexto e critério de sucesso** | funcionalidade, problema, entrada e saída; critério de sucesso da ficha (e, se mudou, por quê) | ½ página |
| **3. Protocolo de comparação** | conjunto de teste; modelo próprio; LLM (modelo, versão, onde roda, parâmetros); versões de prompt testadas; métricas | 1 página |
| **4. Resultados** | quadro comparativo: qualidade, saídas inválidas, latência p50 e p95, custo por mês, dados rotulados, e o que atingiu a meta | 1 página |
| **5. Pipeline de integração** | como a solução escolhida funciona no MVP: prompt, esquema da saída, validação, repetição e fallback; RAG, se houver; chaves, tempo limite, logs | 1 página |
| **6. Exemplos e análise de erros** | pelo menos 3 acertos e 3 erros representativos; erros classificados por tipo | 1 página |
| **7. Limitações e riscos** | cada risco com evidência e mitigação: alucinação, saída inválida, prompt injection, viés, dados pessoais (LGPD), custo, latência, dependência do provedor | ½ a 1 página |
| **8. Decisão final e próximos passos** | decisão, o que a faria mudar e trabalho futuro (ex.: fine-tuning) | ½ página |
| **Declaração de uso de IA generativa** | se e como o grupo usou ferramentas de IA na preparação do documento | 2 a 4 linhas |

O modelo detalha, em cada seção, as perguntas que ela precisa responder.

---

## Rubrica (100 pontos = 60% da nota)

| Critério | Pontos | Excelente (100%) | Bom (75%) | Parcial (50%) | Insuficiente (0 a 25%) |
|---|---|---|---|---|---|
| **C1. Decisão fundamentada** | 25 | decisão clara, coerente com o critério de sucesso definido na ficha e sustentada pelos números; discute o que a faria mudar | decisão clara e apoiada nos números, com ligação fraca ao critério da ficha | decisão apoiada em parte em impressões ou em um único número | decisão sem evidência ou contraditória com os próprios resultados |
| **C2. Protocolo e evidências** | 25 | mesmo conjunto de teste e mesma métrica para todas as abordagens; qualidade, inválidas, latência e custo medidos; ≥ 2 versões de prompt registradas; limitações do tamanho do teste reconhecidas | comparação justa, mas falta uma das medidas ou o registro das versões | comparação com problemas (conjuntos ou métricas diferentes) ou várias medidas ausentes | sem comparação com o modelo próprio, ou números sem origem |
| **C3. Pipeline reprodutível** | 20 | prompt final completo, modelo e versão, parâmetros, esquema da saída, validação, repetição e fallback; integração ao MVP descrita (onde roda, tempo limite, chaves, logs); link do notebook funcionando | pipeline reproduzível, com lacunas pequenas na integração ao MVP | falta o prompt final ou o tratamento da saída | não dá para saber como a solução funciona |
| **C4. Exemplos e análise de erros** | 15 | ≥ 3 acertos e ≥ 3 erros representativos; erros classificados por tipo e comparados entre as abordagens; conclusões tiradas dos erros | exemplos e erros adequados, com análise superficial | só acertos, ou erros sem análise | sem exemplos |
| **C5. Limitações, riscos e mitigação** | 15 | riscos relevantes ao caso, cada um com evidência (teste ou observação) e mitigação concreta; LGPD tratada para os dados reais do MVP | riscos relevantes com mitigação, mas pouca evidência | lista genérica de riscos, sem ligação com o caso | ausente |

**Itens que zeram ou limitam a nota de um critério**
- Exemplos do conjunto de teste usados no few-shot ou no treino do modelo próprio, sem declarar: C2 limitado a 50%.
- Chave de API exposta no documento, no notebook ou no repositório: C3 limitado a 50%.
- Dados pessoais reais no documento ou nos anexos: C5 limitado a 25%.

---

## Checklist antes de enviar

- [ ] A seção 1 diz a decisão **em uma frase** e cita o número principal.
- [ ] O quadro da seção 4 tem o **modelo próprio** e pelo menos **duas versões** do LLM, no mesmo conjunto de teste.
- [ ] Latência e custo estão medidos (não estimados de cabeça) e o volume mensal usado na projeção está declarado.
- [ ] O **prompt final completo** está no anexo, com o nome e a versão do modelo.
- [ ] Há pelo menos **3 erros** analisados.
- [ ] Cada risco da seção 7 tem **evidência** e **mitigação**.
- [ ] Nenhuma chave de API e nenhum dado pessoal real aparecem no documento ou nos anexos.
- [ ] O link do notebook abre para quem não é do grupo.
- [ ] A declaração de uso de IA generativa está preenchida.
- [ ] PDF com até 6 páginas de corpo + `.zip` com os CSVs enviados no Moodle até **05/12, 23h59**.
