# Stage 1: Builder
FROM python:3.11-slim AS builder

WORKDIR /app

# Install dependencies into /app/.local
COPY requirements.txt .
RUN pip install --target=/app/.local -r requirements.txt

# Copy app code
COPY . .

# Stage 2: Runtime (Distroless)
FROM gcr.io/distroless/python3:latest

WORKDIR /app

# Copy app code + dependencies
COPY --from=builder /app /app

# Set Python path for Distroless
ENV PYTHONPATH=/app/.local

# Run Flask
CMD ["app.py"]

