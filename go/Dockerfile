FROM golang:1.20.0-alpine3.17 as builder
WORKDIR /app
COPY ./app .
RUN CGO_ENABLED=0 go build -ldflags="-s -w" -o /hello-world

FROM scratch
COPY --from=builder /hello-world .
ENTRYPOINT [ "./hello-world" ]