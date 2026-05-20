# Econometric Analysis of Southeast Brazil Residential Electricity Demand

Este repositório contém o trabalho prático desenvolvido para a disciplina de **Econometria II** do curso de Ciências Econômicas da **Universidade Federal de Minas Gerais (UFMG)**. 

O objetivo do projeto é modelar e prever o consumo de energia elétrica residencial na Região Sudeste do Brasil utilizando a metodologia Box-Jenkins (modelos SARIMA).

---

## 📌 Visão Geral do Projeto

A análise estuda a série histórica do consumo residencial de energia elétrica (em milhões de MWh) obtida junto à Empresa de Pesquisa Energética (EPE). 

Diante da crise socioeconômica, hídrica e da mudança no regime de bandeiras tarifárias ocorridas em meados da década de 2010, identificou-se uma quebra estrutural no perfil de consumo. Para contornar esse problema e garantir projeções mais estáveis, o modelo foi estimado utilizando o recorte temporal de **janeiro de 2017 a fevereiro de 2026**.

---

## 📊 Principais Pontos e Descobertas

* **Componentes da Série:** A decomposição aditiva revelou uma **tendência nitidamente ascendente** (impulsionada por fatores demográficos e maior adoção de eletrodomésticos) e uma **sazonalidade marcante** associada às estações do ano e ao acionamento de bandeiras tarifárias.
* **Estacionariedade:** Embora os testes de Raiz Unitária (ADF e Phillips-Perron) tenham indicado que a série original era estacionária em torno da tendência (*trend-stationary*), optou-se pela aplicação de uma diferenciação comum e uma sazonalidade para eliminar a memória longa e garantir a robustez dos estimadores.
* **Seleção do Modelo:** Foram testados três modelos candidatos com base nas funções de autocorrelação (FAC e FACP). O **SARIMA$(0,1,1)(0,1,1)_{12}$** ($mod1$) foi selecionado como o modelo ideal por apresentar os menores valores nos critérios de informação AIC (13,09) e BIC (20,82), além de respeitar o princípio da parcimônia.

### Diagnóstico dos Resíduos
* **Invertibilidade:** Todas as raízes inversas do polinômio MA situam-se estritamente dentro do círculo unitário, garantindo a estabilidade das previsões.
* **Ausência de Autocorrelação:** O teste de Ljung-Box obteve um p-valor de 0,18, falhando em rejeitar a hipótese nula de independência serial (resíduos são ruído branco).
* **Normalidade e Homocedasticidade:** O teste de Shapiro-Wilk (p-valor = 0,265) confirmou a normalidade dos erros, e a análise de variância descartou a presença de efeitos ARCH (agrupamentos de volatilidade).

---

## 📈 Validação e Previsão

A validação *ex-post* realizada para o ano de 2025 atestou a alta capacidade preditiva da modelagem temporal:
* **MAPE (Erro Percentual Médio Absoluto):** 2,53% na base de treino e 4,22% na base de teste.
* **U de Theil:** 0,88, comprovando que a especificação proposta apresenta um ganho preditivo superior a modelos de passeio aleatório.

### Projeções Futuras (Ex-Ante)
As previsões médias de consumo geradas para os meses subsequentes de 2026/2027 indicam a manutenção do comportamento sazonal com tendência de crescimento:
* **Março/2026:** 7,50 milhões de MWh
* **Junho/2026 (Baixa temporada):** 6,59 milhões de MWh
* **Janeiro/2027:** 7,54 milhões de MWh




