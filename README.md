# Desenvolvendo sua primeira API com FastAPI, Python e Docker

### Objetivo
Este Desafio de Projeto é um exemplo prático e simplificado de como utilizar FastAPI e outras bibliotecas populares.

### Conceitos
  - FastAPI é um framework Python de alta performance, fácil de aprender, pronto para produção.
  - Docker é uma plataforma de contêiner que permite empacotar e distribuir aplicativos.
  - WorkoutAPI é uma API de competição de crossfit desenvolvida utilizando o framework FastAPI. 

### Pilha da API
  - FastAPI (assíncrono) - Construção da API.
  - Alembic e SQLAlchemy - Migrações e manipulação de banco de dados.
  - Pydantic - Validação de dados.
  - PostgreSQL (via Docker) - Armazenamento de dados.

### Criando o Projeto FastAPI
  - Crie uma pasta para o projeto:

        mkdir fastapi-docker
        cd fastapi-docker
    
  - Crie o arquivo Python main.py:
     
        from fastapi import FastAPI
        app = FastAPI()
        @app.get("/")
        async def root():
          return {"message": "Criando API WorkoutAPI"}


  - Crie um arquivo Dockerfile com o seguinte conteúdo:
    
        FROM python:3.8-slim
        WORKDIR /app
        COPY requirements.txt .
        RUN pip install --no-cache-dir -r requirements.txt

        COPY . .
        CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]

  - Crie um arquivo requirements.txt com as dependências do seu projeto:

        fastapi

  - Construa a imagem do Docker e execute o contêiner:

        docker build -t fastapi-docker .
        docker run -p 8000:8000 fastapi-docker

  - Testando a API

    Para testar sua API faça uma solicitação GET para a URL http://localhost:8000.
    
    Você deve receber a seguinte resposta:

        {"message": "Criando API WorkoutAPI"}

