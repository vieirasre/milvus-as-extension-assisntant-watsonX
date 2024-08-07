# milvus-as-extension-assisntant-watsonX

## faz a reserva 

## coloca o milvus a rodar
usando o notebook da reserva Milvus Example por meio da conexão local.

coneta ao portainer e vê que o milvus está rodando em um container do docker.

inicia o attu para observar se tá funcionndo.

## verifica o docker/milvus
```
docker inspect ibm-lh-milvus
```

## cria coleção

## isere dados 
 sudo yum install java-11-openjdk-devel
# llmSherpa
OU ENTÃO TOCA NO DOCKER (INSTRUÇÕES A BAIXO)
- instala o java
```
 sudo yum install java-11-openjdk-devel
```
- clona llmsherpa
```
git clone https://github.com/nlmatics/llmsherpa.git
cd llmsherpa
```
- install maven
```
sudo yum install maven
```
- instala as dependências:
```
pip install .
```
- clona o ingestor:
```
cd ..
git clone https://github.com/nlmatics/nlm-ingestor.git
```
- instala as dependências:
```
sudo yum install gcc-c++
```

```
cd nlm-ingestor
pip install -r requirements.txt
```
- coloca a rodar o tika:
```
 java -jar nlm-ingestor/jars/tika-server-standard-nlm-modified-2.9.2_v1.jar
```

Abre uma nova linha de comandos 
- instala o ingestor com pip:
```
pip install nlm-ingestor
```
- Run the ingestor:
```
python
```
```
import nltk
nltk.download('punkt')
```
```
exit()
```
```
python -m nlm_ingestor.ingestion_daemon
```

COM DOCKER:
Run the docker file
A docker image is available via public github container registry.

Pull the docker image:
```
docker pull ghcr.io/nlmatics/nlm-ingestor:latest
```
Run the docker image mapping the port 5001 to port of your choice.
```
docker run -p 5001:5001 ghcr.io/nlmatics/nlm-ingestor:latest
```
verifica se está correndo:
```
curl http://localhost:5001/
```




# carregar pdfs para a pasta local

navega até o diretório onde vc vai criar a pasta onde vai colocar os pdfs:
```
cd Documents
```
cria a pasta:
```
mkdir CA_data
```
```
cd CA_data
```
copia o caminho para a pasta:
```
pwd
```

Envia cada um dos documentos para essa pasta:

Abra um terminal no seu computador local e use o seguinte comando scp para copiar o arquivo para a VM:
(acho que também da pra copiar a pasta toda)
```
scp -P <porta> /caminho/para/o/seu/file.pdf watsonx@eu-de.services.cloud.techzone.ibm.com:/caminho/de/destino/na/vm/
```

# USAR PYPDFLOADER 

Instala o tessseract
```
sudo yum install epel-release
sudo yum install tesseract

```

# USAR OLLAMA PARA RESUMIR AS TABELAS 

## RODAR DIRETAMENTE NO SISTEMA 

BAIXAR OLLAMA
```
curl -fsSL https://ollama.com/install.sh | sh
```

verifica a instalação:
```
systemctl status ollama
```

PULL LLAMA3.1
```
ollama pull llama3.1
```

verifica se o modelo está disponível:
```
ollama list
```


## RODAR NO CONTAINER DO DOCKER 

pull da imagem
```
docker pull ollama/ollama:latest
```
na porta 11435 :)
```
docker run -d --name ollama --restart always -p 11435:11434 ollama/ollama:latest
```
pull do llama3.1 no container
```
docker exec -it ollama /bin/bash
```
```
ollama pull llama3.1
```
verifica a lista dos modelos 
```
ollama list
```

```
exit
```




