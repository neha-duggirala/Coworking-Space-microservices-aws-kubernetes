# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Install system dependencies
RUN apt-get update && \
    apt-get install -y build-essential libpq-dev && \
    apt-get clean

# Copy the requirements file into the container at /app
COPY requirements.txt .

# Install any needed packages specified in requirements.txt
RUN pip install --upgrade pip setuptools wheel && \
    pip install -r requirements.txt

# Copy the rest of the application code into the container
COPY . .

# Set environment variables (replace with your actual values)
ENV DB_USERNAME=myuser
ENV DB_PASSWORD=${POSTGRES_PASSWORD}
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5433
ENV DB_NAME=mydatabase

# Expose the port the app runs on
EXPOSE 5153

# Command to run the application
CMD ["python", "app.py"]
