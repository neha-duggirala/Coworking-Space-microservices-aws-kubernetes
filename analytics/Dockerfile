
FROM python:3.9.19-slim

# Set up an app directory for your code
COPY . /app
WORKDIR /app
COPY . .
# Install `pip` and needed Python packages from `requirements.txt`
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

EXPOSE 5000

ENV DB_USERNAME=huynt42
ENV DB_PASSWORD=a123
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5433
ENV DB_NAME=project3DB

# 
CMD ["python", "app.py"]