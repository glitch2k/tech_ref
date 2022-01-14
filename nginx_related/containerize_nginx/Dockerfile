FROM nginx

# USER root



# RUN mkdir zero_fox_layer

WORKDIR /etc/nginx/conf.d

# COPY . .
COPY ./reverse_proxy.conf .

# RUN apt update && apt upgrade -y && \
    # apt install python3-pip -y && \
    # pip install -r requirements.txt


EXPOSE 5000


