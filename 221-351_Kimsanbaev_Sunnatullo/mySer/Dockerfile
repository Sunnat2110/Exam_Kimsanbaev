FROM ubuntu:18.04

# LABEL maintainer= "Кимсанбаев_Суннатулло"

ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update
RUN apt-get install qt5-default -y
RUN apt-get install qtbase5-dev -y
RUN apt-get install qt5-qmake
RUN apt-get install build-essential -y

COPY . .

WORKDIR /root/
RUN qmake -project
RUN qmake
RUN make

ARG SERVER_STRING="Hello, World!!! I am echo server!"
ENV SERVER_STRING_ENV=$SERVER_STRING

CMD ["./myser", "$SERVER_STRING_ENV"]