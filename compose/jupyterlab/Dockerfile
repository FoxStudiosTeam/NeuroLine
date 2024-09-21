FROM ubuntu:22.04 as runtime

COPY requirements.txt /tmp/

WORKDIR /tmp/

EXPOSE 8888

RUN apt update -y
RUN apt install python3.11 python3.11-distutils -y python3-pip
RUN curl -sS https://bootstrap.pypa.io/get-pip.py | python3.11

RUN pip install -r requirements.txt

RUN pip install jupyterlab

WORKDIR /var/lib/foxstudios/neuroline/workspace/data

ENTRYPOINT ["jupyter", "lab", "--allow-root", "--ip=0.0.0.0"]
