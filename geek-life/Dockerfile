FROM golang AS builder

WORKDIR /app

COPY go.mod .
COPY go.sum .
RUN go mod download

ADD . .

RUN go build -o geek-life ./app

FROM ubuntu

WORKDIR /app

COPY --from=builder /app/geek-life .

ENTRYPOINT ["./geek-life"]
