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

## ⚖️ Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para detalhes.



