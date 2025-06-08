# 🔥 FireWatch – Sistema Colaborativo de Prevenção e Alerta contra Incêndios e Calor Extremo

![FireWatch Logo](https://img.shields.io/badge/FireWatch-Sistema%20de%20Prevenção-red)
![Node-RED](https://img.shields.io/badge/Node--RED-v3.0.0-blue)
![MQTT](https://img.shields.io/badge/MQTT-v3.1.1-green)

## 📋 Sobre o Projeto

O FireWatch é um ecossistema digital inovador desenvolvido para prevenir e responder rapidamente a incêndios e ondas de calor. O sistema integra sensores IoT, comunicação MQTT e um dashboard interativo em Node-RED para fornecer monitoramento em tempo real e alertas preventivos.

### 🎯 Objetivos

- Monitoramento em tempo real de condições ambientais
- Detecção precoce de riscos de incêndio
- Sistema de alertas preventivos
- Dashboard interativo para visualização de dados
- Comunicação eficiente entre dispositivos e usuários

## 🛠️ Tecnologias Utilizadas

- **Node-RED**: Plataforma de programação visual para IoT
- **MQTT**: Protocolo de comunicação para IoT
- **HiveMQ**: Broker MQTT público
- **Wokwi**: Simulador de sensores IoT

## 📊 Arquitetura do Sistema

O FireWatch é composto por três componentes principais:

1. **Sensores IoT**:

   - Sensor de temperatura
   - Sensor de fumaça
   - Sensor de CO₂

2. **Gateway de Comunicação**:

   - Broker MQTT (HiveMQ)
   - Protocolo de comunicação MQTT

3. **Dashboard de Monitoramento**:
   - Interface visual em Node-RED
   - Gráficos em tempo real
   - Indicadores de alerta

## 🚀 Configuração e Execução

### Pré-requisitos

- Node.js (versão 14 ou superior)
- Node-RED instalado
- Acesso à internet
- Navegador web moderno

### Instalação

1. Clone o repositório:

```bash
git clone https://github.com/thiago-tonato/gs-iot
cd firewatch
```

2. Instale o Node-RED (caso ainda não tenha):

```bash
npm install -g node-red
```

3. Importe o fluxo do Node-RED:
   - Abra o Node-RED em seu navegador (geralmente em http://localhost:1880)
   - Clique no menu (três linhas) no canto superior direito
   - Selecione "Import"
   - Cole o conteúdo do arquivo `flow.json`

### Executando o Sistema

1. Inicie o Node-RED:

```bash
node-red
```

2. Acesse o dashboard:

   - Abra http://localhost:1880/ui no seu navegador

3. Configure o simulador Wokwi:
   - Acesse o arquivo `wokwi.txt` para obter as configurações do simulador
   - Configure os sensores conforme as especificações

## 📈 Fluxo de Dados

O sistema implementa o seguinte fluxo de dados:

1. **Coleta de Dados**:

   - Sensores simulados enviam dados via MQTT
   - Tópico: `firewatch/sensores`
   - Formato: JSON com campos `temperatura`, `fumaca` e `co2`

2. **Processamento**:

   - Node-RED recebe os dados via broker MQTT
   - Funções de processamento separam os dados por tipo de sensor
   - Dados são normalizados para exibição

3. **Visualização**:
   - Dashboard exibe três medidores (gauges):
     - Temperatura (°C)
     - Fumaça (%)
     - CO₂ (%)
   - Cores indicam níveis de alerta:
     - Verde: Normal
     - Amarelo: Atenção
     - Vermelho: Crítico

## 🔍 Testando o Sistema

1. **Teste de Sensores**:

   - Utilize o simulador Wokwi para gerar dados
   - Verifique a recepção no dashboard
   - Confirme a atualização dos medidores

2. **Teste de Alertas**:
   - Simule valores críticos nos sensores
   - Verifique a mudança de cores nos medidores
   - Confirme a responsividade do sistema

## 📝 Código-Fonte

O projeto está organizado nos seguintes arquivos:

- `flow.json`: Configuração completa do Node-RED
- `wokwi.txt`: Configurações do simulador de sensores

### Estrutura do Fluxo Node-RED

```
[Wokwi Simulator] → [MQTT Broker] → [Node-RED]
    ↓                    ↓              ↓
[Sensores]        → [HiveMQ]     → [Dashboard]
```

---

Desenvolvido com ❤️ para tornar o mundo mais seguro
