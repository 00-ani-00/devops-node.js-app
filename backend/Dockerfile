# Use an official Go runtime as a parent image
FROM golang:1.19

# Set the working directory to /go/src/app
WORKDIR /app

# Copy the current directory contents into the container at /go/src/app
COPY . .

# Build the Go app
RUN go get -d -v ./...
RUN go install -v ./...

# Expose port 8080 to the outside world
EXPOSE 8080

# Command to run the executable
CMD ["./app"]