FROM ubuntu:16.04

RUN apt-get update && apt-get install -y wget ca-certificates \
    git curl vim python3-dev python3-pip \
    libfreetype6-dev libpng12-dev libhdf5-dev

RUN pip3 install --upgrade pip
RUN pip3 install tensorflow
RUN pip3 install numpy pandas sklearn matplotlib seaborn jupyter pyyaml h5py
RUN pip3 install keras --no-deps


WORKDIR /usr/src/app

#copy requirements.txt file into image
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt


#copy py files into image
COPY *.py ./


#copy csv files into image
COPY *.csv ./

#copy kaggle json file to root/.kaggle

RUN ["mkdir", "/root/.kaggle"]

COPY kaggle.json /root/.kaggle

