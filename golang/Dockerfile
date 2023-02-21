FROM golang:1.16.0-alpine3.13 AS builder

WORKDIR /go/src/app
ENV PATH="/go/bin:${PATH}"

COPY ./hello-world.go .

RUN go build hello-world.go

FROM scratch

COPY --from=builder /go/src/app .

CMD ["./hello-world"]