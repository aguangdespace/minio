## minio配置
```
# vim /etc/hosts
192.168.1.1 minio1
192.168.1.2 minio2
# vim /etc/nginx/conf.d/upstream.conf
upstream minio{
        server 127.0.0.1:10005;        #minio
        server minio2:10005;   #minio     
        }

upstream console{
        ip_hash;
        server 127.0.0.1:9090;        #minioc
        server minio2:9090;        #minioc
        }
```
