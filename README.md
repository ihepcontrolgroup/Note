# Note

## docker

#### 1. docker访问宿主机外设地址（/dev/mem)
  ```bash
  sudo docker run --rm -it --name test_mmap --device /dev/mem:/dev/mem --cap-add SYS_RAWIO --user root ubuntu:16.04 /bin/bash
  ```
#### 2. docker新建一个容器
  ```bash
  docker run -it --name example -v /host/path:/docker/path --user root image:tag /bin/bash
  ```
#### 3. docker容器登录到某个用户
  ```bash
  docker start containerID
  docker exec --user username -it containerID /bin/bash
  ```
## samba

#### 1. 更换samba服务的端口号，通过访问本机的1399端口来访问samba服务：
  ```bash
  netsh interface portproxy add v4tov4 listenport=445 listenaddress=127.0.0.1 connectport=1399 connectaddress=192.168.138.1
  ```

## route

#### 1. windows设置永久静态路由
  ```bash
  route -p add 192.168.138.0 mask 255.255.255.0 192.168.31.1
  ```
## markdown

#### 1. 添加图片与标题（当前目录下，居中，80%比例显示）
  ```bash
  <div align=center> 
  <img src=./123.png width = 80%/> 
  <br>
  <div style="color:orange; border-bottom: 1px solid #d9d9d9;
  display: inline-block;
  color: #999;
  padding: 2px;">图1 123</div>
  </div>
  ```
  
## linux

#### 1. 查看使用者user1与python3的进程
  ```bash
  ps -aux | grep user1 | grep python3
  ```
#### 2. 从根目录开始查找所有扩展名为.log的文本文件，并找出包含”ERROR”的行
  ```bash
  find / -type f -name “*.log” | xargs grep “ERROR”
  ```

## latex
#### 1· 将公式中的部分斜体变为直体
- 全局使用
  ```latex
  $\mathrm{ab \times cd = ef}$
  ```
  ![](https://latex.codecogs.com/svg.image?\mathrm{ab&space;\times&space;cd&space;=&space;ef})
- 局部使用
  ```latex
  $\mathrm{ab} \times cd = ef$
  ```
  ![](https://latex.codecogs.com/svg.image?\mathrm{ab}&space;\times&space;cd&space;=&space;ef)
