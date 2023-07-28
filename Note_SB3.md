# Spring Boot 3.0 介紹

## Spring Boot介紹

Spring Boot 是一個開源的、用於簡化和加速 Spring 應用程序開發的框架。它是由 Pivotal 團隊（現在是 VMware）開發和維護的，旨在幫助開發者更快速、更輕鬆地建立高效的生產就緒的 Spring 應用程序。
以下是 Spring Boot 的主要特點和介紹：
* 簡化配置：Spring Boot 採用「註解配置」（Annotation-based Configuration）和「默認配置」（Auto-configuration）的方式，減少了繁瑣的 XML 配置，使開發者只需關注主要業務邏輯而不需要手動配置很多設定。
* 快速開發：Spring Boot 提供了許多快速開發的工具和函式庫，幫助開發者快速構建功能豐富的應用程序。它支援內嵌的伺服器，如Tomcat、Jetty等，無需獨立安裝，只需一個可執行的JAR文件即可運行。
* 自動配置：Spring Boot 依靠自動配置機制，根據應用程序的類型和所使用的依賴庫，自動配置 Spring 應用程序的環境，減少了手動配置的工作量。
* 無需顯式設定：在許多情況下，Spring Boot 可以根據應用程序的需要自動推斷和設定許多屬性，使開發者無需顯式設定很多參數。
* 監控管理：Spring Boot 提供了豐富的健康檢查、監控和管理功能，可以方便地查看應用程序的運行狀態、性能和錯誤信息。
* 集成生態系統：Spring Boot 很好地集成了 Spring 生態系統，並且支援大量第三方庫和工具，方便開發者使用更多功能。
* 開箱即用：Spring Boot 內置了許多常用的功能和組件，如安全性、資料庫訪問、快取、批處理等，開發者可以直接使用這些功能，而無需額外的配置。
* 多種部署選項：Spring Boot 支持多種部署方式，包括傳統的 WAR 包部署，以及嵌入式伺服器部署和容器化部署等。
* 總結來說，Spring Boot 提供了許多便利的功能和工具，讓開發者能夠更加快速、高效地開發 Spring 應用程序，並且使應用程序更易於維護和部署。它在 Spring 社群中廣受歡迎，成為了現代 Java 開發中的首選框架之一。


## Spring Boot 3 部分更新項目
1. JDK支援版本.
  ```
  Spring Boot 3 JDK最低支援版本為17, 並支援較新的JDK19.
  ```
2. GraalVM支援.
  ```
  支援透過GraalVM將應用編譯成可以在本地執行的映像檔.
  
  最低支援版本GrallVM 22.3+ & Native Build Tools Plugin 0.9.17+.
  ```
3. Java EE變更為Jakarta EE.
4. 外部Lib的依賴調整
  ```
  如: Apache ActiveMQ、Atomikos、EhCache2和HazelCast3 移除.
  部分Lib最低版本 : Spring6、Kotlin 1.7+、Lombok 1.18.22+ (JDK17 support支持版本）、Gradle 7.3+ 
  ```
5. 版本依賴
  ```
  Spring Boot 3 依賴Spring 6(最低版本).
  ```
6. Spring MVC調整
  ```
  HttpMethod不再是枚舉
  結尾斜線自適應配置預設為false,可自行更改
  
  ```
   
### 參考資料
* <https://www.youtube.com/watch?v=FvDSL3pSKNQ>
* <https://juejin.cn/post/7165884190028726308>
* <https://juejin.cn/post/7170579125374517278>
