FROM python:3.12-slim

#Diretório onde todos os comandos do contêiner (RUN, COPY, CMD, ADD, ENTRYPOINT) são executados
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY Src/meuSite meuSite

EXPOSE 8000

CMD ["uvicorn","meuSite.main:app","--host","0.0.0.0","--port","8000"]
