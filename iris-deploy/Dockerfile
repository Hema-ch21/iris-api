# Use official Python image
FROM python:3.11-slim

# Set working directory inside container
WORKDIR /app

# Copy requirements.txt (path relative to Dockerfile)
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the app folder (relative to Dockerfile)
COPY app/ ./app/

# Copy the trained model if needed (already inside app)
COPY app/iris_model.pkl ./app/

# Expose port for FastAPI
EXPOSE 8080

# Command to run FastAPI
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8080"]
