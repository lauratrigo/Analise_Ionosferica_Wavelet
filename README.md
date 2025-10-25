# 🌐 Análise de Coerência Wavelet entre Parâmetros Ionosféricos e Dados OMNI

Este projeto contém scripts MATLAB para análise de coerência wavelet entre dados ionosféricos de três estações brasileiras (Araguatins - ARG, São José dos Campos - SJC e Jataí - JAT) e dados solares do conjunto OMNI. A análise visa explorar a relação temporal e espectral entre parâmetros ionosféricos e variáveis solares utilizando técnicas avançadas de processamento de sinais.


## 🛠 Tecnologias Usadas

- MATLAB
- Dados ionosféricos locais (foF2, h'F, hmF2)
- Dados solares OMNI (campos magnéticos, velocidade solar, densidade, índices geomagnéticos)

![MATLAB Badge](https://img.shields.io/badge/MATLAB-R2019b-red)

## 💡 Objetivo

Realizar a análise de coerência wavelet entre sinais ionosféricos e parâmetros solares (OMNI), identificando a correlação espectro-temporal que pode indicar influência solar sobre a ionosfera em diferentes escalas temporais.


## 🚀 Funcionalidades

- Carregamento dos dados ionosféricos pré-processados para cada estação (ARG, SJC, JAT)
- Leitura e pré-processamento dos dados OMNI (dados solares) tratados
- Interpolação temporal dos dados OMNI para alinhar com resolução de 5 minutos dos dados ionosféricos
- Cálculo da coerência wavelet para pares de sinais ionosféricos × dados OMNI
- Geração de gráficos de coerência wavelet para todas as combinações de variáveis
- Visualização com eixos temporais (dias de agosto 2017) e períodos em escala logarítmica (dias)


## 📦 Como Rodar o Projeto

### Passo 1: Preparar os dados ionosféricos

Coloque os arquivos `.mat` correspondentes a cada estação na mesma pasta do script MATLAB:

- `mediasionosfericasARG.mat`
- `mediasionosfericasSJC.mat`
- `mediasionosfericasJAT.mat`

### Passo 2: Preparar os dados OMNI

Coloque o arquivo tabulado `dados_Omni_Tratados.txt` na pasta do projeto. Ele deve conter colunas no formato:

dia mês ano hh:mm Bz Vsw Density E AE SYM/H


### Passo 3: Executar o script correspondente

Para cada estação, execute o script MATLAB correspondente, por exemplo:

```matlab
run analise_coerencia_ARG.m
run analise_coerencia_SJC.m
run analise_coerencia_JAT.m
```
Cada script realizará a análise e gerará os gráficos de coerência wavelet para as variáveis ionosféricas × OMNI.

🔧 Detalhes Técnicos

A resolução temporal dos dados ionosféricos é de 5 minutos (300 segundos).

A interpolação linear alinha os dados OMNI aos tempos dos dados ionosféricos.

Utiliza cwtfilterbank para análise de wavelet e cálculo da coerência wavelet (wcoherence).

Aplicação de extensão simétrica (espelhada) para minimizar efeitos de borda na análise.

Gráficos possuem eixo Y em escala log2 representando períodos em dias.

Eixo X apresenta datas do mês de agosto de 2017 para melhor visualização temporal.

📂 Estrutura do Projeto

```
analise_ionosferica_wavelet/
├── mediasionosfericasARG.mat       # Dados ionosféricos Araguatins (ARG)
├── mediasionosfericasSJC.mat       # Dados ionosféricos São José dos Campos (SJC)
├── mediasionosfericasJAT.mat       # Dados ionosféricos Jataí (JAT)
├── dados_Omni_Tratados.txt         # Dados solares OMNI tratados (tabulado)
├── analise_coerencia_ARG.m         # Script MATLAB análise ARG
├── analise_coerencia_SJC.m         # Script MATLAB análise SJC
├── analise_coerencia_JAT.m         # Script MATLAB análise JAT
└── README.md                       # Documentação do projeto
```
🤝 Agradecimentos

Projeto desenvolvido para estudos em física espacial, processamento de sinais e análise espectro-temporal de dados ionosféricos e solares.

📜 Licença

Este projeto está licenciado sob a Licença MIT - consulte o arquivo LICENSE para detalhes.
