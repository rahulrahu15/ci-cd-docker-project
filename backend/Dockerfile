FROM python:3.11-slim

WORKDIR /app

# Copy requirements.txt from backend folder into container
COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

# Copy all files from backend folder
COPY . .

EXPOSE 5000
CMD ["python", "app.py"]

