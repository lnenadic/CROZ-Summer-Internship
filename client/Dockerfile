# provided base image
FROM bitnami/golang

# working directory
WORKDIR /klijent

# copy the client code file into the container
COPY client.go .

# building the client app
RUN go env -w GO111MODULE=auto && \
    go build -o klijent

# adding a new user bobo
RUN adduser --disabled-password --gecos '' bobo

# bobo as an owner for /klijent
RUN chown -R bobo:bobo /klijent && \
    chmod -R 700 /klijent

# switching to bobo
USER bobo

# expose port for the client code
EXPOSE 8090

# entry point
CMD ["./klijent"]