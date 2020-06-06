FROM golang:1.14.4-alpine3.12
WORKDIR /src
COPY codeeducation.go .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -ldflags '-w -extldflags "-static"' -o codeeducation
FROM scratch
COPY --from=0 /src/codeeducation .
CMD ["./codeeducation"]