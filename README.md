# Nginx JSON log

Nginx docker image with json log format.

### Usage

Set variable $application to your application name, and create a server directive specifying "json" as access_log type, as in the below example.

default.conf example

```
server {

    listen  80;

    set $application 'nginx-jsonlog';

    access_log /var/log/nginx/access.log json;
    error_log  /var/log/nginx/error.log error;

    location / {
        return 200 'hello world';
        add_header Content-Type text/plain;
    }

    location /healthcheck {
        return 200 'healthy';
        add_header Content-Type text/plain;
    }
}
```
