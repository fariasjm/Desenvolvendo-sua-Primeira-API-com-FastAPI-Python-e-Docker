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
    
          return {"message": "Hello, World!"}








