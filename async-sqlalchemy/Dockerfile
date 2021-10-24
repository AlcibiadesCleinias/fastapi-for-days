FROM python:3.8-slim

WORKDIR /opt

COPY src/requirements.txt /opt/.

RUN apt-get update \
    && apt-get install gcc netcat -y \
    && apt-get clean

RUN pip install --no-cache-dir --upgrade -r /opt/requirements.txt

COPY ./src/entrypoint.sh /opt/.
COPY . /opt/

ENTRYPOINT ["/opt/entrypoint.sh"]
CMD ["uvicorn", "main:app", "--reload", "--host 0.0.0.0", "--port 8000"]
