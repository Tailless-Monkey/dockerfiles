FROM alpine

MAINTAINER alpine_nginx (root@unix.cn.com)

RUN echo "http://mirrors.aliyun.com/alpine/latest-stable/main/" > /etc/apk/repositories && echo "http://mirrors.aliyun.com/alpine/latest-stable/community/" >> /etc/apk/repositories && apk update && apk add tzdata && apk add nginx && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && adduser -D -g 'www' www && mkdir /www && chown -R www:www /var/lib/nginx && chown -R www:www www && mkdir /run/nginx && mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.bak

COPY nginx.conf /etc/nginx/
COPY index.html /www/

EXPOSE 80

ENTRYPOINT ["nginx","-g","daemon off;"]
