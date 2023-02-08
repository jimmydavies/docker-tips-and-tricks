FROM python:3.9-slim as base

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

############################################
#                                          #
# Extend Base image with Hello code but    #
# shared dependencies                      #
#                                          #
############################################
FROM base as hello

ENTRYPOINT ["python", "hello.py"]

COPY src/hello.py /app/

############################################
#                                          #
# Extend Base image with Goodbye code but  #
# shared dependencies                      #
#                                          #
############################################
FROM base as goodbye

ENTRYPOINT ["python", "goodbye.py"]

COPY src/goodbye.py /app/

