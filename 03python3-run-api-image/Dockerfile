FROM twheastasia/python3-10-6-base-image

WORKDIR /root

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

RUN apt-get update && apt-get install -y cron
