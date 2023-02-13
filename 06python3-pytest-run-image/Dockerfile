FROM twheastasia/python3-10-6-base-image

WORKDIR /root

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY allure-commandline-2.21.0.zip ./
COPY jdk-17_linux-x64_bin.tar.gz ./

RUN tar -zxvf jdk-17_linux-x64_bin.tar.gz
RUN mv jdk-17.0.6 /opt/jdk
RUN echo "export JAVA_HOME=/opt/jdk" >> ~/.bashrc
RUN echo "export PATH=${JAVA_HOME}/bin:$PATH" >> ~/.bashrc

RUN apt-get update && apt-get install -y unzip
RUN unzip -d /allure allure-commandline-2.21.0.zip
