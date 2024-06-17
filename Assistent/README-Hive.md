## Apache Hive

### Pré-requisitos do Lab
- **Docker Preparado**: Certifique-se de que o Docker está instalado e em funcionamento.
- **Java JDK**: Instale o Java Development Kit (JDK) 8 ou superior.
- **Dados Mocks**: Prepare conjuntos de dados de teste que serão utilizados no Hive.
- **Emulação de Network**: Configuração de rede que simule um ambiente de produção.


### 1. Objetivo do Lab
O objetivo deste laboratório é configurar e utilizar o Apache Hive para consultas e processamento de grandes conjuntos de dados armazenados em Hadoop HDFS. Vamos explorar as principais funcionalidades do Hive, incluindo a criação de tabelas, execução de consultas SQL-like (HiveQL), otimização de consultas e integração com outras ferramentas da sandbox.

### 2. Como Fazer o Setup

#### Variáveis de Ambiente
Adicione as seguintes variáveis de ambiente:
```bash
export HIVE_PORT=10000
export JAVA_HOME=/path/to/java
export PATH=$PATH:$JAVA_HOME/bin
```

#### Especificação de Portas
- **Hive**: 10000

#### Inicialização
Baixe e execute o Docker container do Hive:
```bash
docker pull apache/hive:3.1.2
docker run -d -p 10000:10000 --name hive apache/hive:3.1.2
```

### 3. Descrição dos Passos do Lab

#### Passo 1: Preparar Ambiente

* Exemplo: Instale o Docker usando o Chocolatey no Windows ou apt-get no Ubuntu:
  ```bash
  choco install docker-desktop
  ```
  ou
  ```bash
  sudo apt-get install docker-ce docker-ce-cli containerd.io
  ```
  Certifique-se também de ter o Java JDK instalado e dados mocks disponíveis para os testes.

#### Passo 2: Configurar Hive

* Exemplo: Defina as variáveis de ambiente necessárias no arquivo `.bashrc`:
  ```bash
  export HIVE_PORT=10000
  export JAVA_HOME=/path/to/java
  export PATH=$PATH:$JAVA_HOME/bin
  ```

#### Passo 3: Inicializar Hive

* Exemplo: Baixe e execute o container do Hive:
  ```bash
  docker pull apache/hive:3.1.2
  docker run -d -p 10000:10000 --name hive apache/hive:3.1.2
  ```

#### Passo 4: Criar Tabelas e Carregar Dados

* Exemplo: Utilize o Hive para criar uma tabela de exemplo e carregar dados:
  ```sql
  CREATE TABLE sales (
      id INT,
      product STRING,
      amount DOUBLE
  );
  LOAD DATA LOCAL INPATH '/path/to/data.csv' INTO TABLE sales;
  ```

#### Passo 5: Executar Consultas

* Exemplo: Execute consultas HiveQL para análise dos dados:
  ```sql
  SELECT product, SUM(amount) FROM sales GROUP BY product;
  ```

#### Passo 6: Otimizar Consultas

* Exemplo: Explore o uso de partições e índices para otimização de consultas:
  ```sql
  CREATE TABLE sales_partitioned (
      id INT,
      product STRING,
      amount DOUBLE
  )
  PARTITIONED BY (year INT, month INT);
  ```

#### Passo 7: Integrar com Outras Ferramentas

* Exemplo: Integre o Hive com o Apache Zeppelin para criar visualizações interativas dos dados:
  ```sql
  %hive
  SELECT product, SUM(amount) FROM sales GROUP BY product;
  ```
  E visualize os resultados diretamente no Zeppelin.

### 4. Resultados Esperados
Ao final deste laboratório, espera-se:
- Um ambiente funcional do Apache Hive na porta 10000.
- Capacidade de criar tabelas e executar consultas HiveQL.
- Processamento eficiente de grandes conjuntos de dados.
- Integração bem-sucedida com outras ferramentas da sandbox para análises e integração de dados.
 ---
### 5. Fale Comigo
- **Nome**: Vinicius Antunes Silva
- **Email**: vinicius.antunes@2rpnet.com
- **GitHub**: https://github.com/viniciusantunes26

---

Se precisar de mais alguma coisa ou de outra ferramenta, por favor, me avise!
