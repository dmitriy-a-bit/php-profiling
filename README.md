<h1 align="center">Docker compose deployment for debugging PHP scripts</h1>

---

# Installation
`git clone https://github.com/dmitriy-a-bit/php-profiling.git`  
`cd php-profiling`  
`docker-compose up -d`  

Add entry to hosts file  
`nginx 127.0.0.1`  

## Usage

Jump in php container  
`docker exec -it php-profiling_php_1 bash`  

Execute request on host machine  
`curl nginx/test.php`  

While process started catch needed info with strace inside php container  
`strace -e trace=read -f $(pidof php-fpm | sed 's/\([0-9]*\)/\-p \1/g')`  

Have a fun with strace <3
