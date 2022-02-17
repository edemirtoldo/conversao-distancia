# Kubedev - Desafio Docker - Questão 03

## Aplicação escrita em Python utilizando Flask

Dockerfile
```bash
FROM python:3.8-alpine
WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt
COPY . .
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
```

Processo de construção da imagem com Dockerfile

```bash
docker build -t edemirtoldo/conversao-distancia:v1 .
```

Enviar a imagem v1 para o Docker Hub.

```bash
docker push edemirtoldo/conversao-distancia:v1
```

Vamos fazer um TAG da imagem.

```bash
docker tag edemirtoldo/conversao-distancia:v1 edemirtoldo/conversao-distancia:latest
```

Enviar a imagem latest para o Docker Hub.

```bash
docker push edemirtoldo/conversao-distancia:latest
```

Executar a aplicação Python com Flask em container.

```bash
docker container run -d -p 5000:5000 --name conversao-distancia  edemirtoldo/conversao-distancia:v1
```

Link de acesso a aplicação de conversão de distancia <http://localhost:5000/>

Aplicação Conversão de Distância em Python com Flask

![nodejs](https://github.com/edemirtoldo/conversao-distancia/blob/main/img/conversor-distancia.png)