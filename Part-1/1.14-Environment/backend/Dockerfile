FROM golang

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build

ENV PORT=8080

# Set the frontend origin URL
ENV REQUEST_ORIGIN=http://localhost:5000

CMD ["./server"]

