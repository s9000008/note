# Podman與Docker差異
|  Docker   | Podman  |
|  ----  | ----  |
| 無須root權限  | 需使用root權限 |
| 需常駐程式  | 無常駐程式 |

# Ubuntu下使用Podman建立容器

1. 安裝Podman
  * ```sudo apt-get -y install podman```
2. 建立OCI 註冊表 (Ubuntu下必須建立OCI註冊表)
  * ```
    sudo vim /etc/containers/registries.conf
    
    unqualified-search-registries = ["registry.fedoraproject.org","registry.access.redhat.com", "registry.centos.org", "docker.io"]
    ```
3. 拉取Tomcat映像檔
  * ``` podman pull tomcat:latest (version:  docker.io/library/tomcat:latest ) ```
4. 建立並運行Tomcat容器(沒有同名時會自動進行建立)
  * ```
    podman run -d -p 8080:8080 --name tomcat_container tomcat:latest
    ```
5. 瀏覽localhost:8080, 確認容器是否運行中


```
  404問題修正
  podman exec -it tomcat-server /bin/bash
  mv webapps webapps2
  mv webapps.dist/ webapps
  exit
```
```
停止容器命令
podman stop my_tomcat_container

運行容器命令
podman start my_tomcat_container
```

### 參考資料
* <https://podman.io/docs/installation>
* <https://docs.podman.io/en/latest/Commands.html>
* <https://unixcop.com/apache-tomcat-container-with-podman/>
