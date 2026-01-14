# BackTranslationLLM: Validade de Conteúdo com IA Agêntica 🤖📊

Este projeto implementa uma pipeline automatizada para acelerar o processo psicométrico de **Validade de Conteúdo (CVC)**. Utiliza uma arquitetura de múltiplos agentes de Inteligência Artificial para realizar a tradução reversa (*back-translation*) e a avaliação técnica por um comitê de juízes virtuais.

O objetivo é garantir equivalência semântica, cultural e teórica em instrumentos de medição (escalas, questionários e testes) de forma rápida e rigorosa.

## 🚀 Funcionalidades

- **Pipeline de Tradução de Alta Fidelidade**: Integração com **DeepL API** e refinamento com **Gemini 1.5 Pro**.
- **Back-Translation (Tradução Reversa)**: Verificação automática de integridade semântica comparando o item original com a retrotradução.
- **Comitê de Juízes Virtuais**: Simulação de 5 personas especialistas (Psicometrista, Linguista, Musicoterapeuta PhD, Tradutor Cultural e Clínico).
- **Cálculo Automático de CVC**: Geração de índices de Clareza, Pertinência e Relevância.
- **Relatórios de Raciocínio**: Cada decisão da IA é acompanhada por uma justificativa detalhada (*Chain of Thought*).

## 🏗️ Arquitetura do Sistema

O fluxo de trabalho é dividido em duas fases:

### 1. Pipeline de Tradução e Refinamento
Os agentes trabalham em sequência para garantir que o item traduzido siga regras rígidas (ex: manter-se na primeira pessoa, ser interrogativo, evitar gírias).
- **Modelos**: DeepL API, Gemini 1.5 Flash e Gemini 1.5 Pro.

### 2. Comitê de Juízes para Validade de Conteúdo (CVC)
Painel multidisciplinar que avalia cada item de 1 a 5 em diferentes dimensões.
- **Modelos**: Gemini Pro Preview, Gemma 2 (9b), Gemma (7b) e Gemini Flash.

## 📋 Pré-requisitos

Para executar este projeto, você precisará de:

1.  **Google AI API Key**: [Obtenha aqui](https://aistudio.google.com/).
2.  **DeepL API Key**: [Obtenha aqui](https://www.deepl.com/pro-api).
3.  **Python 3.10+** ou ambiente **Google Colab**.

## ⚙️ Instalação e Uso

1. Clone o repositório:
   ```bash
   git clone https://github.com/FredPedrosa/BackTranslationLLM.git
   ```
2. Configure suas chaves de API no ambiente ou diretamente no notebook.
3. Prepare um arquivo .csv com uma coluna contendo os itens originais.

## 📊 Exemplo de Resultado

O sistema gera uma tabela final com o Coeficiente de Validade de Conteúdo (CVC):

CVC Total (Clareza): ex: 0.857
CVC Total (Pertinência): ex: 0.951
CVC Total (Relevância): ex: 0.951

## 🛠️ Tecnologias Utilizadas

**LLMs**: Google Gemini 1.5 Pro/Flash, Google Gemma 2.
**Tradução**: DeepL API.
**Análise de Dados**: Python, Pandas, Numpy.


## 📁 Estrutura de Arquivos e Entregáveis

A pipeline gera automaticamente uma série de arquivos que documentam cada etapa do processo de validação:

### 📥 Entrada
*   **`CISMA.csv`**: Arquivo original contendo os itens do instrumento no idioma de origem (Espanhol).

### ⚙️ Processamento e Embeddings
*   **`ItensCISMA.csv`**: Versão processada e limpa dos itens para entrada na pipeline.
*   **`embeddingsCISMA.csv`** e **`embeddingsCISMA_originais.csv`**: Representações vetoriais dos itens. Estes arquivos são utilizados para análise de similaridade semântica matemática entre o original e a tradução final. (Para isso, veja o repositório SNA.)

### 📊 Relatórios de Saída (Resultados)
*   **`relatorio_validacao_cvcCISMA.xlsx`**: O principal entregável científico. Contém a planilha completa com as notas de todos os juízes, cálculos de CVC (Clareza, Pertinência e Relevância) e o veredito final por item.
*   **`relatorio_traducao_completoCISMA.html`**: Relatório visual e interativo que permite revisar todo o processo de tradução e as justificativas dos agentes de IA em um navegador.
*   **`traducoes_finaisCISMA.csv`**: Lista final dos itens traduzidos e validados, pronta para uso em aplicações ou pesquisas.
*   **`relatorio_traducao_dadosCISMA.json`**: Dados brutos da execução em formato estruturado, ideal para auditoria técnica ou integração com outros sistemas.

## ⚖️ Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para detalhes.

## 📚 Referências

### Instrumento Original
*   **Vercher, I. B., Soler, A. A., & Ferrari, K. D. (2023).** CUESTIONARIO CISMA - CUESTIONARIO DEL IMPACTO DE LAS SESIONES DE MUSICOTERAPIA EN PACIENTES ADULTOS. *Brazilian Journal of Music Therapy*, (33). [https://doi.org/10.51914/brjmt.33.2022.385](https://doi.org/10.51914/brjmt.33.2022.385)

### Metodologia de Validação (CVC)
*   **Hernández-Nieto, R. A. (2002).** *Contributions to Statistical Analysis*. Mérida: Universidad de los Andes. (Referência utilizada para o cálculo do Coeficiente de Validade de Conteúdo e ponto de corte de 0.80).

### Referência para este repositório
*   Pedrosa, F. G. (2025). *BackTranslationLLM: Pipeline automatizada para Validade de Conteúdo com IA Agêntica*. Disponível em: https://github.com/FredPedrosa/backtranslationllm
