FROM python:3.9-slim as app

ENTRYPOINT ["python", "hello.py"]
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY src/hello.py /app/

############################################
#                                          #
# Extend App image with test requirements  #
# and utilities                            #
#                                          #
############################################
FROM app as test

COPY tests tests

RUN pip install -r tests/requirements.txt

ENTRYPOINT ["pytest", "tests"]
