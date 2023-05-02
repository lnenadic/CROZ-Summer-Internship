# provided base image
FROM quay.io/mlrun/python:3.7.11-slim

# working directory in the container
WORKDIR /app

# copy the Python file and requirements into the container
COPY main.py /app/
COPY requirements.txt /app/

# install the dependencies from requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# expose the port on which the server will listen
EXPOSE 8000

# start the server using uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0"]