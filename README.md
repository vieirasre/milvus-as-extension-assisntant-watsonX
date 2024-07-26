# milvus-as-extension-assisntant-watsonX

## faz a reserva 

## coloca o milvus a rodar

## cria coleção

## isere dados 
 sudo yum install java-11-openjdk-devel
### llmSherpa

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

- 

