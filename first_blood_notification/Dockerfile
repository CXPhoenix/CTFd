FROM python:3.11-alpine

COPY ./requirements.txt /requirements.txt
RUN pip install --no-cache -r /requirements.txt

COPY ./crontab.txt /etc/crontabs/root
COPY ./resolv.conf /etc/resolv.conf

WORKDIR /opt/notification

COPY ./src .

CMD [ "crond", "-f", "&&", "tail", "-f", "/dev/null" ]