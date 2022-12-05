FROM debian:bullseye-slim
RUN apt update &&\
    apt install-y lib32gcc1 tar wget &&\
    mkdir /steam &&\
    wget http://media.steampowered.com/client/steamcmd_linux.tar.gz &&\
    tar -xf ttp://media.steampowered.com/client/steamcmd_linux.tar.gz &&\
    mv steamcmd.sh /steam &&\
    mv linux32 /steam &&\
    rm steamcmd_linux.tar.gz
WORKDIR /steam
RUN ./steamcmd.sh +quit

