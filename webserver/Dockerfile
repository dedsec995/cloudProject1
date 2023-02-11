FROM ubuntu:18.04
RUN apt-get update; apt-get install -y gnupg2 
RUN apt-get install -y apt-utils
COPY ./requirements.txt /app/requirements.txt
WORKDIR /app
RUN apt-get install -y python3
RUN apt-get install -y python3-pip
COPY . /app
RUN pip3 install -r requirements.txt
ENTRYPOINT [ "python3" ]
CMD ["run.py" ]