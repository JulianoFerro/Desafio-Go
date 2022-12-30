FROM golang:1.19-alpine as go

WORKDIR /go/src/app
COPY /app/ .
RUN go run main.go
RUN go build -ldflags "-w" main.go

FROM scratch
WORKDIR /root
COPY --from=go /go/src/app/main .
CMD [ "./main" ]