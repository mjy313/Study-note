仅限于GIT上代理，去下载外网的资源：

**1.**
	首先你的windows宿主机必须是有代理的，查看软件的端口，查看主机的ip地址
	然后通过例子：
git config --global http.proxy http://127.0.0.1:7897
git config --global https.proxy http://127.0.0.1:7897
**127.0.0.1更换为自己的IP地址，7897是up的软件端口。**
	需要注意的是这里不可以写127.0.0.1，这个地址是指的WSL2的地址。
	
	
**永久全局生效**
1.打开配置文件：nano ~/.bashrc
2.在文件末尾添加：
\	# 固定代理设置 (IP: 10.189.82.201) 

export http_proxy="http://10.189.82.201:7897"

export https_proxy="http://10.189.82.201:7897

这里的7897端口改为自己的，ip地址换成你自己主机的ip，我的主机是10.189.82.201，WIN_IP=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}')会自动获取宿主机的ip。

3.source ~/.bashrc执行这个使其配置生效





如果终端没有用UTF-8格式，上传的文件为中文名的话，就会出现乱码

git config --global core.quotepath false

通过这个命令修复乱码问题