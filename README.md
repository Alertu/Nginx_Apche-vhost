# Nginx-vhost:

server {
        listen        80; #端口
        server_name  127.0.0.1; # 服务器地址
        root   "/";
        location / {
            index index.php index.html error/index.html;
            error_page 400 /error/400.html;
            error_page 403 /error/403.html;
            error_page 404 /error/404.html;
            error_page 500 /error/500.html;
            error_page 501 /error/501.html;
            error_page 502 /error/502.html;
            error_page 503 /error/503.html;
            error_page 504 /error/504.html;
            error_page 505 /error/505.html;
            error_page 506 /error/506.html;
            error_page 507 /error/507.html;
            error_page 509 /error/509.html;
            error_page 510 /error/510.html;
            include /;
            autoindex  off;
        }
        location ~ \.php(.*)$ {
            fastcgi_pass   127.0.0.1:9000;
            fastcgi_index  index.php;
            fastcgi_split_path_info  ^((?U).+\.php)(/?.+)$;
            fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
            fastcgi_param  PATH_INFO  $fastcgi_path_info;
            fastcgi_param  PATH_TRANSLATED  $document_root$fastcgi_path_info;
            include        fastcgi_params;
        }
}


# Apahe-vhost:

<VirtualHost _default_:80>
DocumentRoot "D:\phpStudy\PHPTutorial\WWW\ren\frontend\website"
ServerName 10.0.4.60:80
</VirtualHost>
