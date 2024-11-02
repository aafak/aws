# To install a sample go APP inside ec2 instance and access it
While creating the instance, Add the following user data in additional details

```
#!/bin/bash
# Update package list and install Go
sudo apt update -y
sudo apt install -y golang -y

# Create a directory for the Go application
mkdir -p /home/ubuntu/myapp
cd /home/ubuntu/myapp

# Create a simple Go web server
sudo cat <<EOF > main.go
package main

import (
    "fmt"
    "log"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "<h1>Hello from EC2!</h1><p>Hostname: %s</p><p>IP Address: %s</p>", r.Host, r.RemoteAddr)
}

func main() {
    http.HandleFunc("/", handler)
    log.Println("Starting server on :8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        log.Fatalf("Server failed to start: %v", err)
    }
}
EOF

# Initialize a Go module (required for Go builds)
sudo go mod init myapp
# Build the Go application
sudo go build -o myapp main.go
# Run the Go application on port 8080
nohup ./myapp > /home/ubuntu/myapp/myapp.log 2>&1 &
```
