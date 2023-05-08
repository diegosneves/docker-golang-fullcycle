FROM golang:alpine AS Builder

WORKDIR /app

COPY . .

RUN go mod init app

RUN go build -ldflags "-s -w" -o app .

FROM scratch

COPY --from=Builder /app/app /

CMD ["/app"]

