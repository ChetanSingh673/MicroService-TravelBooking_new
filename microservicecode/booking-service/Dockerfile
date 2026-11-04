# Stage 1: Build the Go application
FROM golang:1.21-alpine AS build
WORKDIR /app

# Copy dependency files first for better caching
COPY go.mod go.sum ./
RUN go mod download

# Copy source code and compile
COPY . .
RUN go mod tidy && CGO_ENABLED=0 GOOS=linux go build -o booking-service .

# Stage 2: Run the compiled application

FROM alpine:3.19
RUN apk --no-cache add ca-certificates tzdata
WORKDIR /app
COPY --from=build /app/booking-service .
EXPOSE 3003
CMD ["./booking-service"]
