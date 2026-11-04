# Grandes Modelos de Linguagem (2026)

> Repositório da disciplina **Grandes Modelos de Linguagem** — Bloco 03 da **Residência Tecnológica em Engenharia de Software Inteligente** (FACOM/UFMS).

[![Abrir no Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bmnogueira-ufms/LLM-ESIA-2026)

---

## Sumário
- [Visão geral](#visão-geral)
- [Ementa e objetivos](#ementa-e-objetivos)
- [Cronograma](#cronograma)
- [Avaliação](#avaliação)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Como usar (Colab ou local)](#como-usar-colab-ou-local)
- [Bibliografia](#bibliografia)
- [Contato](#contato)

---

## Visão geral
Esta disciplina fecha o Bloco 03 e antecede o **Demo Day**. Ela apresenta os fundamentos dos grandes modelos de linguagem (LLMs) e um caminho complementar — muitas vezes mais rápido — para adicionar inteligência ao MVP de cada grupo: em vez de (ou além de) treinar um modelo próprio, avaliar se um LLM resolve melhor o problema.

- **Docente:** Prof. Bruno Nogueira (FACOM/UFMS)
- **Período:** 04/11/2026 a 05/12/2026
- **Carga horária:** 15 h — 9 h síncronas (2 aulas + oficina) e 6 h assíncronas
- **Encontros síncronos:** remotos, às quartas, 19h–22h (horário de MS)
- **Linguagem:** Python · **Ambiente:** Google Colab
- **Principais bibliotecas:** Hugging Face Transformers, tiktoken, BertViz, scikit-learn, OpenAI SDK (para APIs compatíveis)

---

## Ementa e objetivos
**Ementa:** Tokenização. Modelos de atenção. Arquitetura Transformers. Modelos encoder-decoder. Modelos encoder-only. Modelos decoder-only.

**Objetivo geral:** capacitar os residentes a compreender os fundamentos dos grandes modelos de linguagem e a decidir, de forma fundamentada, se e como integrar um LLM à funcionalidade inteligente do MVP do grupo.

**Ao final, você será capaz de:**
1. Explicar como um texto é convertido em tokens e o impacto da tokenização em custo e janela de contexto, em especial para o português.
2. Descrever o mecanismo de atenção e os componentes da arquitetura Transformer.
3. Distinguir as famílias encoder-only, encoder-decoder e decoder-only, seus objetivos de pré-treino e aplicações típicas.
4. Aplicar técnicas de prompting e de saída estruturada para resolver tarefas com LLMs.
5. Reconhecer quando usar RAG ou fine-tuning leve em vez de apenas prompting.
6. Comparar um LLM com o modelo próprio construído no bloco, considerando desempenho, custo, latência e riscos.
7. Prototipar a integração de um LLM ao MVP e documentar as decisões tomadas.

---

## Cronograma

| Data | Modalidade | Atividade | Material |
|---|---|---|---|
| 04/11 (qua), 19h–22h | Síncrona | **Aula 1** — Fundamentos: tokenização, atenção, Transformer e famílias de modelos | [`aula01/`](aula01/) |
| 05/11 a 18/11 | Assíncrona | **Aula 2** — Notebook guiado + ficha do caso de uso | [`aula02/`](aula02/) |
| 18/11 (qua), 19h–22h | Síncrona | **Aula 3** — Uso prático de LLMs: prompting, RAG, fine-tuning leve e avaliação | em breve |
| 25/11 (qua) | Síncrona | **Oficina aplicada** — prototipação da integração ao MVP | em breve |
| 29/11 a 05/12 | Assíncrona | Finalização da integração e do documento de entrega | em breve |

---

## Avaliação

| Instrumento | Quando | Peso |
|---|---|---|
| Ficha do caso de uso (em grupo) | até 18/11 | 20% |
| Protótipo e demonstração na oficina (em grupo) | 25/11 | 20% |
| Documento final (em grupo) | até 05/12 | 60% |

---

## Estrutura do repositório
```bash
.
├── aula01/                         # Aula 1 — Fundamentos
│   └── aula01_demo.ipynb           # notebook das demonstrações ao vivo
├── aula02/                         # Aula 2 — Atividade assíncrona
│   ├── aula02_notebook_guiado.ipynb# Parte A — notebook guiado (individual)
│   ├── ficha_caso_de_uso.md        # Parte B — modelo da ficha (em grupo)
│   ├── ficha_caso_de_uso.docx      # o mesmo modelo, em Word
│   └── conjunto_teste_modelo.csv   # formato sugerido do conjunto de teste
├── dados/
│   └── chamados_exemplo.csv        # 60 chamados fictícios (4 categorias) usados no notebook guiado
├── images/                         # figuras
├── requirements.txt                # dependências para uso local
└── README.md
```

---

## Como usar (Colab ou local)

### Google Colab (recomendado)
1. Abra o notebook pelo botão **Open in Colab** no topo de cada notebook (ou pelo *badge* deste README).
2. **Arquivo → Salvar uma cópia no Drive**, para não perder suas alterações.
3. **Ambiente de execução → Alterar o tipo de ambiente de execução → GPU T4.**
4. Rode as células de preparação (Seção 0).

**Chaves de API:** se for usar uma API (opção B do Exercício 4 da Aula 2), guarde a chave nos **Secrets do Colab** (ícone 🔑) com o nome `LLM_API_KEY`. Nunca coloque chaves no código nem no GitHub.

### Ambiente local (venv)
```bash
git clone https://github.com/bmnogueira-ufms/LLM-ESIA-2026
cd LLM-ESIA-2026
python -m venv .venv
source .venv/bin/activate          # Windows (PowerShell): .venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```

---

## Bibliografia

**Básica**
- JURAFSKY, D.; MARTIN, J. H. *Speech and Language Processing*. 3. ed. (rascunho on-line). Stanford University.
- CASELI, H. M.; NUNES, M. G. V. (org.). *Processamento de Linguagem Natural: conceitos, técnicas e aplicações em português*. 2. ed. BPLN, 2024.
- TUNSTALL, L.; VON WERRA, L.; WOLF, T. *Natural Language Processing with Transformers*. O'Reilly, 2022.
- ALAMMAR, J.; GROOTENDORST, M. *Hands-On Large Language Models*. O'Reilly, 2024.

**Complementar**
- SENNRICH, R.; HADDOW, B.; BIRCH, A. Neural Machine Translation of Rare Words with Subword Units. ACL, 2016.
- VASWANI, A. et al. Attention Is All You Need. NeurIPS, 2017.
- DEVLIN, J. et al. BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding. NAACL, 2019.
- RAFFEL, C. et al. Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer. JMLR, 2020.
- BROWN, T. et al. Language Models are Few-Shot Learners. NeurIPS, 2020.
- SOUZA, F.; NOGUEIRA, R.; LOTUFO, R. BERTimbau: Pretrained BERT Models for Brazilian Portuguese. BRACIS, 2020.
- LEWIS, P. et al. Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks. NeurIPS, 2020.
- HU, E. et al. LoRA: Low-Rank Adaptation of Large Language Models. ICLR, 2022.
- WEI, J. et al. Chain-of-Thought Prompting Elicits Reasoning in Large Language Models. NeurIPS, 2022.
- ALAMMAR, J. *The Illustrated Transformer* (blog).
- HUGGING FACE. *LLM Course* (curso on-line).

---

## Contato
**Prof. Bruno Nogueira — FACOM/UFMS**
E-mail: bruno.nogueira@ufms.br
