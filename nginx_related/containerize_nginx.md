## **serve static content from 1 virtual server within a container**
* create a simple nginx container using the cli command
    * ```
        docker run -itd -p 8080:80 --name my_nginx nginx
    ```
* bind mount a local folder & config file to the nginx config file for dev/testing
    * ```
        docker run -itd -p 8080:80 -v "$(pwd)"/bind_mount:/etc/nginx/conf.d/ --name my_nginx nginx
    ```
* create a file called *"default.conf"* to edit nginx configs
* enter the following in the *"default.conf"* file
    * ```
        server {
            listen       80;                    # listening on port 80
            server_name  localhost;             # will response to request with "localhost" in the address field

            location / {                        # denotes the "endpoint" that will be used to serve the static content
                root   /usr/share/nginx/html;   # folder containing static content
                index  index.html index.htm;    # static content files to be served
                }
            }
    ```

## **serve static content from multiple virtual servers within a container**

## **https serve static content from 1 virtual server within a container**

## **https serve static content from multiple virtual servers within a container**
