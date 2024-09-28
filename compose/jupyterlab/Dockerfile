FROM tensorflow/tensorflow:latest-gpu as runtime

COPY requirements.txt /tmp/

WORKDIR /tmp/

EXPOSE 8888

#TODO REMOVE IT OR REPLACE IMAGE @FROM
RUN apt update -y
RUN apt install python3.11 python3.11-distutils -y python3-pip
RUN curl -sS https://bootstrap.pypa.io/get-pip.py | python3.11

RUN pip install -r requirements.txt

RUN pip install tensorflow[and-cuda]
RUN pip install jupyterlab
RUN pip install ultralytics
RUN apt-get update && apt-get install ffmpeg libsm6 libxext6  -y


WORKDIR /var/lib/foxstudios/neuroline/workspace/data

ENTRYPOINT ["jupyter", "lab", "--allow-root", "--ip=0.0.0.0"]
