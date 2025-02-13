FROM python:3.12-slim AS builder 

#Diretório onde todos os comandos do contêiner (RUN, COPY, CMD, ADD, ENTRYPOINT) são executados
WORKDIR /app

COPY pyproject.toml requirements.txt ./

RUN pip wheel --no-cache-dir -r requirements.txt -w wheels
RUN pip install --no-cache-dir --no-deps --find-links=wheels -r requirements.txt

COPY Src Src
RUN pip wheel --no-cache-dir --no-deps --wheel-dir wheels .

FROM python:3.12-slim AS runner

COPY --from=builder /app/wheels /wheels
RUN pip install --no-cache /wheels/* && rm -rf /wheels

EXPOSE 8000

CMD ["uvicorn","meuSite.main:app","--host","0.0.0.0","--port","8000"]
