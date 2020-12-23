1.brew install nginx
2.brew services start nginx
3.访问[http://localhost:8080/](http://localhost:8080/) 验证nginx已启动
4.启动php-fpm
5.修改nginx的配置文件/usr/local/etc/nginx/nginx.conf
```server{
        listen 8080;
        server_name //host地址;
        location / {
            root           //web目录;
            fastcgi_pass   127.0.0.1:9000;
            fastcgi_index  index.php;
            fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
            include        fastcgi_params;
            try_files $uri $uri/ /index.php?$args;
        }
        rewrite ^/(.*) /index.php last;

    }
```
6. nginx -s reload
