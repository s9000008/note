# Spring Boot 2 升級至 Spring Boot 3 注意事項

1.	確保專案可以於JDK17的環境下進行編譯與執行.
2.	若專案為Spring Boot 2.X的版本,請將專案先升級至Spring Boot 2.7版本,並確認是否可以正常執行.
3.	確認2.7版本中的依賴項是否在3後的版本發生異動.
4.	若專案有使用Spring Security ,請先將Spring Security升級至5.8 .
5.	更改Maven parent中 Spring Boot版本至3.0.0 .
   ```maven
<parent> 
     <groupId>org.springframework.boot</groupId> 
     <artifactId>spring-boot-starter-parent</artifactId> 
     <version> 3.0.0 </version>
      <relativePath/> <!-- 查找父級存儲庫 --> 
</parent>
  ```
7.	Spring Boot2 中棄用或是不推薦的classes, methods, properties , annotations在Spring Boot3版本已被移除,當升級為3.0後須修復錯誤與替換.
8.	Spring Boot3 中調整了部分配置屬性的名稱,可以透過添加依賴後運行,確保相關配置屬性的變更並在```完成後將該依賴移除```.
   ```maven
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-properties-migrator</artifactId>
	<scope>runtime</scope>
</dependency>
```
10.	 javax開頭的package請改為jakarta ,在 Spring Boot3 中Java EE相關API大多改為Jakarta EE.(javax.sql.* 與 javax.crypto.*例外)
11.	 Spring Boot3 核心部分調整
  * 應用執行時,在Console中顯示的Spring Banner不再支援圖片請改為txt.
  * 預設的日誌(Logback、Log4j2)日期格式更改為 ISO-8601("yyyy-MM-dd’T’HH:mm:ss.SSSXXX"). 
    (若需套用舊格式可以使用logging.pattern.dateformat或是LOG_DATEFORMAT_PATTERN 環境變數)
  * @ConstructingBinding不再需要@ConstructorBinding
  * YamlJsonParser 已被刪除,若有使用到請改用其他JsonParser實作的解析器.
13.	 Web應用更動
  * HttpMethod從枚舉改為實體Class
  * Spring MVC 和 WebFlux URL 中的結尾斜線自適應設置改為false. (例如: @GetMapping("/member/register") , 當你呼叫URI為/member/register/時,回傳會是404)
  * Jetty不支援Servlet 6.0, Servlet API需降級為5.0
14. Hibernate 預設為6.1版本

### 參考資料
* <https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.0-Migration-Guide>
* <https://www.1ju.org/article/spring-boot-3-spring-6-new>
* <https://javatechonline.com/how-to-migrate-spring-boot-2-to-spring-boot-3/#Step1_Install_JDK_17_in_your_System>
* <https://blog.csdn.net/hadues/article/details/128159873>

  
   	 
