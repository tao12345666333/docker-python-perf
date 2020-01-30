FROM python:3.7-alpine
ENV FILENAME=alpine-perf-py3.json

WORKDIR /app

RUN apk add --no-cache gcc musl-dev linux-headers
# Install performance suite
RUN python3 -m pip install pyperformance

# Run benchmarks
RUN pyperformance run --python=python3 -o $FILENAME

RUN python3 -m perf stats $FILENAME
