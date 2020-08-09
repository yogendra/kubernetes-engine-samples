FROM golang:1.8-alpine
ADD . /go/src/hello-app
RUN go install hello-app

FROM alpine:latest
RUN adduser -D -u 1000  app 
USER 1000
COPY --from=0 /go/bin/hello-app .
ENV PORT 8080
CMD ["./hello-app"]
