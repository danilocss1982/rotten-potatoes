### Imagem base utilizada.
FROM python:3.8-slim-buster

### Descrição do autor.
LABEL Author="Danilo C S Santos" Email="danilocss@gmail.com" 

### Diretório padrão de trabalho dentro do container.
WORKDIR /app

### Copiando arquivos para serem instalados.
COPY requirements.txt .

### Instalando pacotes e dependências.
RUN python -m pip install -r requirements.txt

### Copiando projeto.
COPY . /app

### Expondo porta 5000.
EXPOSE 5000

### Principal processo de execução do container.
CMD ["gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "-c", "config.py", "app:app"]