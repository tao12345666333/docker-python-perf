FROM python:3.7-stretch
ENV FILENAME=stretch-perf-py3.json

WORKDIR /app

# Install performance suite
RUN python3 -m pip install performance

# Run benchmarks
RUN pyperformance run --python=python3 -o $FILENAME

RUN python3 -m perf stats $FILENAME
