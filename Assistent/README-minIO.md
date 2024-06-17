
---

# MinIO Sandbox

## 1.Objetivo

O objetivo deste ambiente de laboratório é permitir que você explore e aprenda sobre o MinIO, um sistema de armazenamento de objetos de alta performance e escalável. Você será capaz de configurar o MinIO, criar buckets, carregar dados e interagir com ele através de exemplos práticos.

### Pré-requisitos do Lab

- **Imagem Utilizada:** `docker.io/minio/minio:RELEASE.2024-01-01T16-36-33Z`
- **Portas Mapeadas:**
  - `9000:9000`: Mapeamento da porta 9000 do container para a porta 9000 do host
  - `9001:9001`: Mapeamento da porta 9001 do container para a porta 9001 do host
- **Comando de Inicialização:** `server /data --console-address ":9001"`
  - Define o comando a ser executado quando o container do MinIO iniciar
- **Volumes Mapeados:**
  - `./volume/minio/data:/data`: Mapeamento do diretório de dados do MinIO
- **Rede Utilizada:** `default-network`
  - Define a rede na qual o serviço MinIO será executado

Essas configurações garantem que o serviço MinIO seja configurado e executado corretamente no ambiente Docker. Certifique-se de ajustar os caminhos dos volumes e as versões da imagem conforme necessário para o seu ambiente específico.

## 2. **Configurar o MinIO**

   Defina as variáveis de ambiente necessárias no arquivo `.bashrc`:

   ```bash
   export MINIO_ACCESS_KEY=minio_user
   export MINIO_SECRET_KEY=minio_password
   ```

3. **Inicializar o MinIO**

   Baixe e execute o container do MinIO:

   ```bash
   docker run -p 9000:9000 --name minio \
     -e "MINIO_ACCESS_KEY=minio_user" \
     -e "MINIO_SECRET_KEY=minio_password" \
     minio/minio server /data
   ```

4. **Criar Buckets e Carregar Dados**

   Utilize o cliente `mc` do MinIO para criar buckets e carregar dados:

   ```bash
   mc mb mybucket
   mc cp /path/to/local/file mybucket/
   ```

## Descrição dos Passos do Lab

1. **Preparar Ambiente**

   Instale o Docker utilizando o Chocolatey no Windows ou apt-get no Ubuntu:

   ```bash
   choco install docker-desktop
   ```

   ou

   ```bash
   sudo apt-get install docker-ce docker-ce-cli containerd.io
   ```

   Certifique-se também de ter o Java JDK instalado e dados mocks disponíveis para os testes.

2. **Configurar MinIO**

   Defina as variáveis de ambiente necessárias no arquivo `.bashrc`:

   ```bash
   export MINIO_ACCESS_KEY=minio_user
   export MINIO_SECRET_KEY=minio_password
   ```

3. **Inicializar MinIO**

   Baixe e execute o container do MinIO:

   ```bash
   docker run -p 9000:9000 --name minio \
     -e "MINIO_ACCESS_KEY=minio_user" \
     -e "MINIO_SECRET_KEY=minio_password" \
     minio/minio server /data
   ```

4. **Criar Buckets e Carregar Dados**

   Utilize o cliente `mc` do MinIO para criar buckets e carregar dados:

   ```bash
   mc mb mybucket
   mc cp /path/to/local/file mybucket/
   ```

## Resultados Esperados

Ao seguir esses passos, você atingirá os seguintes objetivos:

1. **Configuração do MinIO:**
   - Configurar corretamente o ambiente Docker para execução do MinIO.
   - Definir e exportar as variáveis de ambiente necessárias para autenticação no MinIO.

2. **Inicialização do MinIO:**
   - Baixar e executar o container do MinIO.
   - Garantir que o MinIO esteja funcionando corretamente e acessível na porta especificada.

3. **Criação de Buckets:**
   - Utilizar o cliente `mc` do MinIO para criar buckets.
   - Verificar se os buckets foram criados com sucesso e estão disponíveis para armazenamento de objetos.

4. **Carregamento de Dados:**
   - Utilizar o cliente `mc` para carregar dados em um bucket existente.
   - Confirmar que os dados foram carregados com sucesso e estão acessíveis no MinIO.

5. **Exploração das Capacidades do MinIO:**
   - Testar a escalabilidade do MinIO criando e gerenciando diversos buckets e objetos.
   - Avaliar o desempenho do MinIO ao realizar operações de leitura e escrita em larga escala.

Ao completar esses objetivos, você estará familiarizado com o processo de configuração, utilização e teste do MinIO para armazenamento de objetos, podendo explorar suas capacidades de armazenamento escalável e de alto desempenho de forma eficiente.

 ---
### 5. Fale Comigo
- **Nome**: Vinicius Antunes Silva
- **Email**: vinicius.antunes@2rpnet.com
- **GitHub**: https://github.com/viniciusantunes26

---

Se precisar de mais alguma coisa ou de outra ferramenta, por favor, me avise!
