# Observabilidade com APM usando Grafana, Prometheus, Tempo e OpenTelemetry

Este repositório contém um ambiente configurado para monitoramento e rastreamento de aplicações usando Grafana, Prometheus, Tempo e OpenTelemetry Collector. Ele permite observar métricas, logs e traces em tempo real, fornecendo uma solução completa para observabilidade.

## Estrutura do Projeto

```bash
observabilidade/
├── docker-compose.yml          # Arquivo Docker Compose para configurar os serviços
├── etc/                        # Configurações do sistema
│   ├── dashboards/             # Dashboards Grafana personalizados
│   │   └── OpenTelemetry-APM.json
│   ├── dashboards.yaml         # Configuração para provisionar dashboards no Grafana
│   ├── grafana/                # Configuração de datasources do Grafana
│   │   └── datasource.yml
│   ├── otel-collector-config.yaml  # Configuração do OpenTelemetry Collector
│   └── prometheus.yml          # Configuração do Prometheus
└── readme.md                   # Este arquivo
```

## Serviços configurados

### Grafana

- Porta: 3000
- Acesso sem autenticação habilitado.
- Dashboards personalizados configurados para observabilidade de APM.

### Prometheus

- Porta: 9090
- Coleta de métricas configurada.

### Tempo

- Porta: 14250
- Backend local para armazenamento de traces.


### OpenTelemetry Collector

    - Portas:
      -- 4317: OTLP gRPC
      -- 4318: OTLP HTTP
      -- 8889: Interface de monitoramento
    - Configurado para enviar dados ao Tempo e Prometheus.

### Pré-requisitos

    - Docker e Docker Compose instalados no sistema.

## Como Executar

1. Clone este repositório:

```
git clone https://github.com/gomesrocha/observabilidade.git
cd observabilidade
```

2. Inicie os serviços:

```
docker-compose up -d
```

3. Acesse as ferramentas:

    - Grafana: http://localhost:3000

## Dashboards Grafana

- Os dashboards estão configurados automaticamente ao iniciar o Grafana. Você pode encontrar os dashboards personalizados na interface do Grafana em Dashboards > Manage > OpenTelemetry-APM.

### Configuração
#### Grafana

- O arquivo de configuração do datasource está localizado em ./etc/grafana/datasource.yml.

#### OpenTelemetry Collector

- As configurações do OpenTelemetry Collector estão em ./etc/otel-collector-config.yaml.

#### Prometheus

- A configuração do Prometheus está em ./etc/prometheus.yml.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar PRs para melhorias e correções.
