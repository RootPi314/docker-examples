# compiler container
FROM golang:alpine as build
ENV CGO_ENABLED=1
ADD . .
RUN go build -o /main

# runtime container
FROM scratch
COPY --from=build /main /main
ENTRYPOINT ["/main"]
