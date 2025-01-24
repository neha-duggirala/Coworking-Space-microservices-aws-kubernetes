
FROM public.ecr.aws/docker/library/python:3.9-slim

# Set up an app directory for your code
COPY . /app
WORKDIR /app
COPY . .
# Install `pip` and needed Python packages from `requirements.txt`
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

EXPOSE 5153

ENV DB_USERNAME=myuser
ENV DB_PASSWORD=mypassword
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5433
ENV DB_NAME=mydatabase

CMD ["python", "app.py"]