# 💡 Simulação Contínua de Sinais EMG em Tempo Real

Este notebook implementa uma simulação contínua de sinais EMG (Eletromiografia) em tempo real, processando buffers de dados e extraindo características para classificação. Abaixo está uma visão geral das funcionalidades e etapas implementadas.

---

## 📋 Visão Geral

- **Simulação de sinais EMG**: Processamento de buffers contínuos de dados EMG, como em uma aquisição ao vivo.
- **Filtros**: Aplicação de filtros Notch e Bandpass para remoção de ruídos e seleção de frequências relevantes.
- **Extração de características**: Cálculo de métricas no domínio do tempo e da frequência para análise dos sinais.
- **Classificação**: Treinamento de um classificador SVM para prever rótulos com base nas características extraídas.
- **Visualização**: Gráficos para análise de sinais filtrados, janelas segmentadas e espectrogramas.

---

## 🛠️ Funcionalidades

### 1. **Filtros**
- **Filtro Notch**: Remove ruídos de 60 Hz (frequência da rede elétrica).
- **Filtro Bandpass**: Seleciona frequências entre 5 Hz e 50 Hz, típicas de sinais EMG.

### 2. **Extração de Características**
- **Domínio do Tempo**:
    - Variância (`var`)
    - RMS (Root Mean Square)
    - Comprimento de Onda (`wl`)
    - Contagem de Zeros (`zc`)
- **Domínio da Frequência**:
    - Densidade Espectral de Potência (`PSD`)
    - Frequência Média (`fmn`)
    - Frequência Média do Módulo (`mmnf`)

### 3. **Simulação em Tempo Real**
- Processamento de buffers de 1600 amostras.
- Segmentação em janelas de 256 amostras com sobreposição.
- Extração de características e classificação em tempo real.

### 4. **Classificação**
- **Modelo SVM**: Treinamento de um classificador SVM com kernel RBF para prever rótulos de atividade muscular.

### 5. **Visualização**
- Sinais filtrados.
- Janelas segmentadas no domínio do tempo.
- Espectrogramas (STFT) para análise no domínio da frequência.

---

## 📂 Estrutura do Código

1. **Funções de Filtro e Extração de Características**:
     - Implementadas para processar os sinais EMG e calcular métricas relevantes.

2. **Simulação em Tempo Real**:
     - Função `simulate_realtime` para processar buffers e prever rótulos.

3. **Treinamento do Classificador**:
     - Treinamento de um modelo SVM com dados segmentados e características extraídas.

4. **Simulação Contínua**:
     - Processamento de um arquivo contínuo de 12800 amostras, dividido em buffers de 1600 amostras.

5. **Visualização**:
     - Gráficos para análise dos sinais e validação do processamento.

---

## 🚀 Como Usar

1. **Pré-requisitos**:
     - Python 3.x
     - Bibliotecas: `numpy`, `matplotlib`, `scipy`, `sklearn`

2. **Passos**:
     - Carregue os dados EMG no formato `.npy`.
     - Execute as células para aplicar filtros, extrair características e treinar o classificador.
     - Simule o processamento contínuo com buffers de dados.
     - Visualize os resultados com os gráficos gerados.

---

## 📊 Exemplos de Visualização

- **Sinal Filtrado**:
    - Gráfico do sinal original e após aplicação dos filtros.
- **Janela Segmentada**:
    - Exemplo de uma janela no domínio do tempo.
- **Espectrograma**:
    - Representação no domínio da frequência usando STFT.

---

## ✅ Resultados

- Classificador SVM treinado com dados EMG segmentados.
- Predições realizadas em tempo real para cada buffer processado.
- Visualizações que validam o processamento e a extração de características.
---

## 📧 Autores

- João Victor Piloni Vilhegas
- Carolina Yumi Fujii