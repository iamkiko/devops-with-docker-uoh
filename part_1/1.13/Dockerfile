FROM golang:1.16

WORKDIR /app

COPY . .

# Build project
RUN go build -o server

# Set port as 8080
ENV PORT 8080

# Run server binary
CMD ["./server"]
