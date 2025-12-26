# ------------------------
# Stage 1: Build Stage
# ------------------------
FROM python:3.11-slim AS builder

WORKDIR /app

# Copy requirements and install to local directory
COPY requirements.txt .
RUN pip install --user --no-cache-dir -r requirements.txt

# Copy app code
COPY . .

# ------------------------
# Stage 2: Runtime Stage (Distroless)
# ------------------------
FROM gcr.io/distroless/python3:latest

WORKDIR /app

# Copy Python packages from builder
COPY --from=builder /root/.local /root/.local
ENV PATH=/root/.local/bin:$PATH

# Copy app code
COPY --from=builder /app /app

# Run Flask app
CMD ["app.py"]

