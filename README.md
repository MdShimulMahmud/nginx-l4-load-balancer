## Configuring **nginx** for Layer 4 Load Balancer

We know that nginx works as a
 - Reverse Proxy, 
 - Load Balancer and
 - Web Server.

There are two types of load balancers:
- Layer 4 load balancer (http protocol)
- Layer 7 load balancer (tcp protocol)

## Repository Setup

To work with this repository, follow these steps:

1. Clone the repository to your local machine:
    
    ```sh
    git clone git@github.com:MdShimulMahmud/nginx-l4-load-balancer.git
    cd nginx-l4-load-balancer
    ```

1. Build Docker images:
    - app1 
        ```sh
        cd app1
        docker build -t app1 .
        docker run app1
        ```
    - app2

        ```sh
        cd app2
        docker build -t app2 .
        docker run app2
        ```
    - lb

        ```sh
        cd lb
        docker build -t lb .
        docker run -p 80:80 lb
        ```

## Testing the Load Balancer

To check if the load balancer is working properly, run the following command:

```sh
curl http://localhost:80
```

If you encounter an error related to the `nginx.conf` file's `backend_servers` IP addresses, you can inspect the network to find the IP addresses of your `app1` and `app2` containers. Run the following command and replace the IP address with your machine's IP:

```sh
docker inspect network
```

