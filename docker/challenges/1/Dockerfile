FROM golang:1.18.3-alpine as compilation

WORKDIR /app

COPY main.go /app/main.go

RUN go build main.go


FROM scratch as runtime

WORKDIR /app

COPY --from=compilation /app/main /app/main

CMD ["./main"]