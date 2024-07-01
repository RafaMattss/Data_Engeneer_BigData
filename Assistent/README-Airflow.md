## Apache Airflow
1. Pré-requisitos do Lab
- Docker Preparado: Certifique-se de que o Docker está instalado e em funcionamento.
- Java JDK: Instale o Java Development Kit (JDK) 8 ou superior.
- Tecnologias Adjacentes e suas Versões:
  - Apache Airflow: 2.x
  - Docker: Compatível com seu sistema operacional
  - PostgreSQL: 11-alpine
  - Redis: latest
- Dados Mocks: Prepare conjuntos de dados de teste que serão utilizados nas DAGs do Airflow.
- Emulação de Network: Configuração de rede que simule um ambiente de produção.
- Chocolatey: Certifique-se de que todos os pré-requisitos necessários estão liberados no nosso chocolatey, como:
  - openjdk8
  - docker
2. Como Fazer o Setup
- Variáveis de Ambiente
- Adicione as seguintes variáveis de ambiente:
```bash
export AIRFLOW__CORE__EXECUTOR=CeleryExecutor
export AIRFLOW__DATABASE__SQL_ALCHEMY_CONN=postgresql+psycopg2://admin:admin@postgres/metastore_db
export AIRFLOW__CELERY__RESULT_BACKEND=db+postgresql://admin:admin@postgres/metastore_db
export AIRFLOW__CELERY__BROKER_URL=redis://:@redis:6379/0
export AIRFLOW__CORE__FERNET_KEY=''
export AIRFLOW__CORE__DAGS_ARE_PAUSED_AT_CREATION=true
export AIRFLOW__CORE__LOAD_EXAMPLES=false
```
- Especificação de Portas
  - Airflow Webserver: 8081
  - PostgreSQL: 5432
  - Redis: 6379
- Inicialização
  - Baixe e execute os containers do Docker para os serviços necessários
4. Resultados Esperados
- Ambiente Airflow Funcionando: O Apache Airflow deve estar acessível na porta 8081.
- Criação e Execução de Workflows:
- Capacidade de criar DAGs interativos.
- Agendamento e execução de tarefas através do Airflow.
- Monitoramento de workflows através da interface web do Airflow.
- Integração com Outras Ferramentas da Sandbox:
  - Conectividade e interação com outras ferramentas como PostgreSQL, Redis, e MinIO, permitindo a execução de tarefas que envolvam múltiplas tecnologias.
  - Capacidade de utilizar dados armazenados no MinIO, executar jobs no Apache Spark, e consultar tabelas no Apache Hive diretamente a partir do Airflow.
  - Implementação de workflows complexos que integrem diferentes componentes da sandbox, demonstrando a flexibilidade e interoperabilidade do Airflow. 
