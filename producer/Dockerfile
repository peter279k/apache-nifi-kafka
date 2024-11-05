FROM python:alpine

WORKDIR /app
ADD app .


ADD  requirements.txt .

RUN  apk update \
     && apk add git \
     && pip install -r requirements.txt \
     && pip uninstall -y kafka-python \
     && pip install --break-system-packages git+https://github.com/dpkp/kafka-python.git

CMD [ "python", "main.py" ]
