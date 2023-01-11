**GCP install Tomcat**

參考網址
> https://bytesofgigabytes.com/googlecloud/installing-apache-tomcat-on-google-cloud/

參考影片
> https://www.youtube.com/watch?v=Jf6UudGWpiE

```
//使用super user全縣
sudo su
//前往根目錄
cd /
安裝JDK
sudo apt-get install default-jdk
//在根目錄建立tomcat folder
mkdir tomcat
//確認建立成功
ls
//移動至tomcat目錄
cd tomcat
//安裝tomcat
sudo wget https://mirrors.estointernet.in/apache/tomcat/tomcat-8/v8.5.78/bin/apache-tomcat-8.5.78.zip
//安裝壓縮工具
sudo apt-get install unzip
//解壓縮
sudo unzip apache-tomcat-8.5.78.zip

cd apache-tomcat-8.5.78/bin/

chmod 700 *.sh
./startup.sh

建立防火牆規則
如果初始選擇允許 HTTP/HTTPS流量,直接在該防火牆規則上添加port即可(,逗點分隔)
瀏覽器 IP + port

```

#### 問題處理:

1. sudo: wget: command not found
` sudo apt-get install wget `
參考網址:
https://itslinuxfoss.com/wget-command-not-found/


2. tomcat 安裝command 回傳 `404 Not Found`
前往連結 : http://mirrors.estointernet.in/apache/tomcat/tomcat-8/
確認版本號並更改安裝指令
`sudo wget https://mirrors.estointernet.in/apache/tomcat/tomcat-8/v＜版本號在這＞/bin/apache-tomcat-＜版本號在這＞.zip`
範例: `https://mirrors.estointernet.in/apache/tomcat/tomcat-8/v8.5.78/bin/apache-tomcat-8.5.78.zip`

