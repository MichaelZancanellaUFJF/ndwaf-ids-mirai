# Sistema de Detecção de Intrusão para Redes IoT

## Visão Geral
Este projeto apresenta um framework para treinamento e avaliação de modelos de aprendizado de máquina voltados para a construção de um **Sistema de Detecção de Intrusão (IDS)**, com foco na identificação de tráfego malicioso em redes IoT, especialmente ataques da botnet **Mirai**. 

A abordagem utiliza os modelos de aprendizado de máquina **Random Forest (RF)** e **LightGBM (LGBM)**, aproveitando suas características de eficiência computacional e robustez para detecção de anomalias.

## Arquitetura Proposta
O sistema é baseado em um modelo **Fog-Core-Cloud**, onde:
- **Edge Layer:** Coleta de dados em tempo real de dispositivos IoT.
- **Fog Layer:** Processamento e detecção de tráfego anômalo em tempo real, utilizando o **Network Data Analytics Function (NWDAF)**.
- **Cloud Layer:** Treinamento e atualização de modelos usando o **Model Training Logical Function (MTLF)** e armazenamento de dados históricos no **Analytical Data Repository Function (ADRF)**.

O sistema visa fornecer um IDS eficiente, com resposta rápida na Fog e treinamento contínuo de modelos na Cloud para aprimoramento da detecção de novas ameaças.

## Dataset Utilizado
O projeto utiliza o dataset **CICIoT2023**, contendo:
- Tráfego benigno e tráfego malicioso gerado pela botnet Mirai.
- Um total de **40 milhões de linhas**, processadas em chunks para otimização do treinamento.
- Seleção de **14 features relevantes** para melhorar a precisão dos modelos.

## Modelos Utilizados
Foram treinados e comparados dois modelos de aprendizado de máquina:
- **Random Forest (RF)**
  - Tempo de treinamento: **10m19s**
  - Acurácia: **97,62%**
- **LightGBM (LGBM)**
  - Tempo de treinamento: **2m41s**
  - Acurácia: **97,58%**

## Como Executar
O projeto está disponível em um **notebook Jupyter (.ipynb)** que já contém as partes de treinamento dos modelos.

1. Clone o repositório:
   ```sh
   git clone https://github.com/MichaelZancanellaUFJF/ndwaf-ids-mirai.git
   ```
2. Instale as dependências:
   ```sh
   pip install -r requirements.txt
   ```
3. Abra o notebook Jupyter e execute as células para treinar os modelos:
   ```sh
   jupyter notebook 5G - NWDAF - IDS.ipynb
   ```
4. Para realizar inferência, utilize a função já implementada no notebook.

## Resultados
| Modelo  | Acurácia | Precisão | Revocação | F1-score | Tempo de Treinamento |
|---------|----------|-----------|-----------|----------|---------------------|
| RF      | 97,62%   | 97,63%    | 97,62%    | 97,62%   | 10m19s              |
| LGBM    | 97,58%   | 97,59%    | 97,58%    | 97,58%   | 2m41s               |


## Contato
Caso tenha dúvidas ou queira contribuir, entre em contato:
- **Nome:** MICHAEL VITOR ZANCANELLA BARBOZA
- **E-mail:** michael.zancanella@ufjf.br
- **GitHub:** [MichaelZancanellaUFJF](https://github.com/MichaelZancanellaUFJF/ndwaf-ids-mirai)

