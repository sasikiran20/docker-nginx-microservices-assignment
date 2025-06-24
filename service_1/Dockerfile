FROM golang:1.22-alpine

WORKDIR /app

COPY main.go .

RUN go build -o service1 main.go

EXPOSE 8001

CMD ["./service1"]
