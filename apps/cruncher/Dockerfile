# syntax=docker/dockerfile:1
FROM golang:1.21-alpine AS builder

WORKDIR /src
COPY . .
RUN go mod download
RUN go build -o /bin/app .

##########################################################
FROM scratch
COPY --from=builder /bin/app app
EXPOSE 8080
CMD ["./app"]
