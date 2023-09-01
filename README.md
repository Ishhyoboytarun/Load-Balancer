# Load Balancer with Reverse Proxy

This is a simple implementation of a load balancer using a reverse proxy in Go. It distributes incoming HTTP requests across multiple backend servers using a round-robin algorithm. This README provides an overview of the code and how to use it.

## Prerequisites

Before using this code, make sure you have the following prerequisites installed:

- Go: [Install Go](https://golang.org/doc/install) if you haven't already.

## Getting Started

1. Clone this repository to your local machine:

   ```shell
   git clone https://github.com/Ishhyoboytarun/Load-Balancer
   ```

2. Navigate to the project directory:

   ```shell
   cd load-balancer-reverse-proxy
   ```

3. Build and run the load balancer:

   ```shell
   go run main.go
   ```

   The load balancer will start on `localhost` at port `8000`.

## Configuration

The load balancer is configured in the `main` function of the `main.go` file. You can add or remove backend servers by creating instances of the `simpleServer` type and adding them to the `servers` slice.

```go
servers := []Server{
    newSimpleServer("https://www.facebook.com"),
    newSimpleServer("https://www.bing.com"),
    newSimpleServer("https://www.duckduckgo.com"),
}
```

You can customize the load balancer's behavior by modifying the code according to your specific requirements.

## How it Works

- The load balancer listens for incoming HTTP requests on the specified port.
- When a request is received, it selects the next available backend server in a round-robin fashion.
- The selected backend server processes the request using a reverse proxy and forwards the response back to the client.

## Error Handling

Error handling in this code is minimal and is designed for demonstration purposes. In a production environment, you should implement more robust error handling strategies.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

This code is a simple example of a load balancer with a reverse proxy in Go. It can serve as a starting point for more complex load balancing solutions tailored to your specific needs.

Feel free to explore, modify, and use this code as a foundation for your own projects. If you have any questions or feedback, please don't hesitate to reach out.

Enjoy load balancing your web applications!
