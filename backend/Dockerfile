# syntax=docker/dockerfile:1
FROM golang:1.16-alpine AS build

RUN mkdir /app
WORKDIR /app
COPY go.mod ./
COPY go.sum ./
COPY * ./
RUN go mod download
COPY *.go ./
RUN go build -o /docker-gs-ping
EXPOSE 9000
CMD [ "/docker-gs-ping" ]