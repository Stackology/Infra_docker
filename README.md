# Laboratorio de Redes em docker 

Este projeto foi criado para simular um ambiente  completo de infraestrutura de redes com Docker, 
com oobjetivo de testar a integração, desempenho e especialização de diversos bancos de dados e ferramentas de monitoramento.
Ele pode ser utilizado como laboratorio local para aprendizado e experimentos.

Objetivos:

Criar um infraestrutura que reflita casos deuso reais, distribuindoas responsabilidades entre serviços especializados:

- PostgresSQL: Armazenamento principal de dados relacionais.
- Redis: Cache em memória para acelerar leituras frequentes e armazenar estruturas voláteis.
- Neo4j: Banco de dados orientado a gráfos para representar redes de conexões complexas.
- MongoDB: Armazenamento flexivel para dados semi-estruturados (JSON, XML, etc.).
- InfluxDB: Armazenamento de series temporais (metricts, logs, evetos).
- Elasticsearch: Indexação e buscas textuais em grandes volumes de dados.
- Prometheus: Coletade de metricas de serviços e bancos de dados.
- Grafana: Visualização e monitoramento de metricas e dashboards.

# Estrutura do Projetos


    infra/
    ├── docker-compose.yml          # Arquivo principal da infraestrutura
    ├── prometheus/
    │   └── prometheus.yml          # Configuração dos targets do Prometheus
    ├── grafana/
    │   └── provisioning/           # (opcional) Dashboards e datasources customizados
    └── README.md                   # Este arquivo explicativo



# Como Utilizar

## 1- Pré-requisitos:

    - Docker e Docker Compose instalados

## 2- Executar os containers:


    docker-compose up -d


## 3- Acessos principais:

    - PostgreSQL: localhost:5432
    - Redis: localhost:6379
    - Neo4j: localhost:7474 (web) / 7687 (bolt)
    - MongoDB: localhost:27017
    - InfluxDB: localhost:8086
    - Elasticsearch: localhost:9200
    - Prometheus: localhost:9090
    - Grafana: localhost:3000 (usuário: admin / senha: admin)

# Possíveis Expansões

- Adição de HAProxy ou Nginx para balanceamento de carga
- Clustering de bancos (ex: PostgreSQL com réplica, Redis Sentinel, etc)
- Integração com ferramentas CI/CD como Jenkins ou GitLab Runner
- Persistência via volumes nomeados para testes de resiliência