# BackTranslationLLM: Validade de Conteúdo com IA Agêntica 🤖📊

Este projeto implementa uma pipeline automatizada para acelerar o processo psicométrico de tradução e levantamento de **validade de conteúdo** de testes. Para tanto, utiliza uma arquitetura de múltiplos agentes de Inteligência Artificial que realiza a tradução reversa (*back-translation*) e a estimação do Coeficiente de Validade de Conteúdo (CVC; Hernández-Nieto, 2002) por um comitê de juízes virtuais.

O objetivo é garantir equivalência semântica, cultural e teórica em instrumentos de medição (escalas, questionários e testes) de forma rápida e rigorosa.

## 🚀 Funcionalidades
*   **Pipeline de Tradução de Alta Fidelidade**: Integração com DeepL API e refinamento com Gemini 1.5 Pro.
*   **Back-Translation (Tradução Reversa)**: Verificação automática de integridade semântica comparando o item original com a retrotradução.
*   **Comitê de Juízes Virtuais**: Simulação de 5 personas especialistas (Psicometrista, Linguista, Musicoterapeuta PhD, Tradutor Cultural e Clínico).
*   **Cálculo Automático de CVC**: Geração de índices de Clareza, Pertinência e Relevância.
*   **Relatórios de Raciocínio**: Cada decisão da IA é acompanhada por uma justificativa detalhada (*Chain of Thought*).

## 🏗️ Arquitetura do Sistema
O fluxo de trabalho é dividido em duas fases automatizadas:

1.  **Pipeline de Tradução e Refinamento**: Sequência de quatro agentes especializados (Tradutor, Verificador, Juiz de Qualidade e Refinador) que garantem a adesão a regras metodológicas rígidas.
2.  **Comitê de Juízes para levantamento de CVC**: Um painel multidisciplinar de LLMs que avalia cada item em uma escala Likert de 5 pontos.

## 📈 Análise Estatística e Validação Psicométrica (R)
Para validar cientificamente os resultados, este repositório inclui o script especializado **`CISMA.R`**. Ele realiza o *benchmark* entre o comitê de IA e juízes humanos.

*   **Análise de Grafo Exploratória (EGA)**: Compara a estrutura de rede dos itens originais vs. traduzidos.
*   **Informação Mútua Normalizada (NMI)**: Cálculo da concordância estrutural (NMI = 1.0 no estudo de caso).
*   **Embeddings Semânticos**: As representações vetoriais utilizadas para análise de similaridade foram geradas utilizando o modelo **GPT-3.5-Turbo** (OpenAI), garantindo alta precisão na captura de significados latentes.
*   **Visualização de Dados**: Gera automaticamente as figuras de alta resolução (CVC comparativo e Correlação de Spearman) para publicação.

> **Nota de Reprodutibilidade:** O script `CISMA.R` está configurado para carregar os dados diretamente deste repositório, permitindo a replicação imediata dos resultados.

## 📋 Pré-requisitos
*   **Python 3.10+**: Necessário para a pipeline agêntica (Requer chaves de API Google AI e DeepL).
*   **R 4.0+**: Necessário para o script `CISMA.R`. 
    *   *Bibliotecas:* `EGAnet`, `psych`, `patchwork`, `ggplot2`, `irr`, `dplyr`, `tidyr`, `readxl`, `DiagrammeR`.

## ⚙️ Instalação e Uso
1.  Clone o repositório:
    ```bash
    git clone https://github.com/FredPedrosa/backtranslationllm.git
    ```
2.  Para análise estatística, abra o RStudio e execute o arquivo `CISMA.R`.

## 📁 Estrutura de Arquivos Principais
*   `CISMA.py`: Código principal da pipeline de IA.
*   `CISMA.R`: Script de análise psicométrica e geração de figuras.
*   `embeddingsCISMA.csv`: Dados vetoriais dos itens (gerados via GPT-3.5-Turbo).
*   `relatorio_validacao_cvcCISMA.xlsx`: Resultados brutos da validação por IA.

## ⚖️ Licença
Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para detalhes.

## 📚 Referências
*   **Vercher, I. B., et al. (2023).** Cuestionario CISMA. *Brazilian Journal of Music Therapy*.
*   **Hernández-Nieto, R. A. (2002).** *Contributions to Statistical Analysis*. Mérida: Universidad de los Andes.
*   **Pedrosa, F. G. (2025).** *BackTranslationLLM: Pipeline automatizada para Validade de Conteúdo com IA Agêntica*. https://github.com/FredPedrosa/backtranslationllm/
