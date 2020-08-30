FROM pytorch/pytorch:0.4.1-cuda9-cudnn7-devel

WORKDIR /app

RUN apt-get -y update && apt-get -y install \
        libgl1-mesa-glx \
        libglib2.0-0 \
        libsm6 \
        libxrender-dev \
        libxext6 \
        unzip \
        wget \
        nano 

RUN pip install --upgrade pip 

RUN pip install --upgrade --ignore-installed certifi

RUN pip install --upgrade cython \
                pillow \
                matplotlib \
                opencv-contrib-python \
                tqdm \
                pillow

RUN wget -O OPN.pth "https://www.dropbox.com/s/sxo25p12sfc7na7/OPN.pth?dl=1"
RUN wget -O TCN.pth "https://www.dropbox.com/s/nihciqj551xv7a8/TCN.pth?dl=1"

# Finally copy all files over
COPY . . 

ENTRYPOINT ["python", "demo_group_image.py"]