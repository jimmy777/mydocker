FROM golang:1.9.4

RUN mkdir -p /go/src/test

WORKDIR /go/sec/test

COPY main.go .

RUN CGO_ENABLED=0 GOOS=linux go build -o app .

CMD ["./app"]

