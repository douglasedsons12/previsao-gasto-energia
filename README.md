# Econometric Analysis of Southeast Brazil Residential Electricity Demand

[cite_start]Este repositório contém o trabalho prático desenvolvido para a disciplina de **Econometria II** do curso de Ciências Econômicas da **Universidade Federal de Minas Gerais (UFMG)**[cite: 1, 2, 3]. 

[cite_start]O objetivo do projeto é modelar e prever o consumo de energia elétrica residencial na Região Sudeste do Brasil utilizando a metodologia Box-Jenkins (modelos SARIMA)[cite: 4, 8, 122].

---

## 📌 Visão Geral do Projeto

[cite_start]A análise estuda a série histórica do consumo residencial de energia elétrica (em milhões de MWh) obtida junto à Empresa de Pesquisa Energética (EPE)[cite: 8, 14]. 

[cite_start]Diante da crise socioeconômica, hídrica e da mudança no regime de bandeiras tarifárias ocorridas em meados da década de 2010, identificou-se uma quebra estrutural no perfil de consumo[cite: 9, 10]. [cite_start]Para contornar esse problema e garantir projeções mais estáveis, o modelo foi estimado utilizando o recorte temporal de **janeiro de 2017 a fevereiro de 2026**[cite: 11, 39].

---

## 📊 Principais Pontos e Descobertas

* [cite_start]**Componentes da Série:** A decomposição aditiva revelou uma **tendência nitidamente ascendente** (impulsionada por fatores demográficos e maior adoção de eletrodomésticos) e uma **sazonalidade marcante** associada às estações do ano e ao acionamento de bandeiras tarifárias[cite: 12, 51, 52, 59].
* [cite_start]**Estacionariedade:** Embora os testes de Raiz Unitária (ADF e Phillips-Perron) tenham indicado que a série original era estacionária em torno da tendência (*trend-stationary*), optou-se pela aplicação de uma diferenciação comum e uma sazonalidade para eliminar a memória longa e garantir a robustez dos estimadores[cite: 77, 78, 79, 93].
* [cite_start]**Seleção do Modelo:** Foram testados três modelos candidatos com base nas funções de autocorrelação (FAC e FACP)[cite: 115, 116]. [cite_start]O **SARIMA$(0,1,1)(0,1,1)_{12}$** ($mod1$) foi selecionado como o modelo ideal por apresentar os menores valores nos critérios de informação AIC (13,09) e BIC (20,82), além de respeitar o princípio da parcimônia[cite: 117, 122, 134].

### Diagnóstico dos Resíduos
* **Invertibilidade:** Todas as raíces inversas do polinômio MA situam-se estritamente dentro do círculo unitário, garantindo a estabilidade das previsões[cite: 137, 138].
* [cite_start]**Ausência de Autocorrelação:** O teste de Ljung-Box obteve um p-valor de 0,18, falhando em rejeitar a hipótese nula de independência serial (resíduos são ruído branco)[cite: 155, 156].
* [cite_start]**Normalidade e Homocedasticidade:** O teste de Shapiro-Wilk (p-valor = 0,265) confirmou a normalidade dos erros, e a análise de variância descartou a presença de efeitos ARCH (agrupamentos de volatilidade)[cite: 195, 196, 207].

---

## 📈 Validação e Previsão

[cite_start]A validação *ex-post* realizada para o ano de 2025 atestou a alta capacidade preditiva da modelagem temporal[cite: 224, 232]:
* [cite_start]**MAPE (Erro Percentual Médio Absoluto):** 2,53% na base de treino e 4,22% na base de teste[cite: 238].
* **U de Theil:** 0,88, comprovando que a especificação proposta apresenta um ganho preditivo superior a modelos de passeio aleatório[cite: 239].

### Projeções Futuras (Ex-Ante)
As previsões médias de consumo geradas para os meses subsequentes de 2026/2027 indicam a manutenção do comportamento sazonal com tendência de crescimento[cite: 256, 267]:
* [cite_start]**Março/2026:** 7,50 milhões de MWh [cite: 268]
* [cite_start]**Junho/2026 (Baixa temporada):** 6,59 milhões de MWh [cite: 268]
* **Janeiro/2027:** 7,54 milhões de MWh [cite: 268]

---

