FROM python:3.7-slim
ENV FILENAME=slim-perf-py3.json

WORKDIR /app

# Install performance suite
RUN apt update \
        && apt install -y gcc \
        && python3 -m pip install performance

# Run benchmarks
RUN pyperformance run --python=python3 -o $FILENAME

RUN python3 -m perf stats $FILENAME
