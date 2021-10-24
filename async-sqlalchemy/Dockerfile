FROM python:3.8-slim

WORKDIR /opt

COPY src/requirements.txt /opt/requirements.txt

RUN apt-get update \
    && apt-get install gcc -y \
    && apt-get clean

RUN pip install --no-cache-dir --upgrade -r /opt/requirements.txt

COPY . /opt/

CMD ["uvicorn", "main:app", "--reload", "--host 0.0.0.0", "--port 8000"]
