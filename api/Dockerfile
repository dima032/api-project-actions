# Stage 1: Test
FROM python:3.12-slim AS tester
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
RUN pytest

# Stage 2: Final image
FROM python:3.12-slim AS final
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "app.py"]
