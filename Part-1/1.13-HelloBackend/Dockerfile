FROM golang

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build

ENV PORT=8080
ENV REQUEST_ORIGIN=https://example.com

CMD ["./server"]

