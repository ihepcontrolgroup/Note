# Note

## docker

### 1. docker访问宿主机外设地址（/dev/mem)
  ```bash
  sudo docker run --rm -it --name test_mmap --device /dev/mem:/dev/mem --cap-add SYS_RAWIO --user root ubuntu:16.04 /bin/bash
  ```

## samba

### 1. 更换samba服务的端口号，通过访问本机的1399端口来访问samba服务：
  ```bash
  netsh interface portproxy add v4tov4 listenport=445 listenaddress=127.0.0.1 connectport=1399 connectaddress=192.168.138.1
  ```

## route

### 1. windows设置永久静态路由
    ```bash
    route -p add 192.168.138.1 192.168.31.1
    ```
