FROM golang:1.19 AS builder
WORKDIR /go/src/calculator_service
COPY app/ .
RUN CGO_ENABLED=0 go build -a calculator.go

FROM scratch 
COPY --from=builder /go/src/calculator_service/calculator /
CMD ["/calculator"]
EXPOSE 8080
