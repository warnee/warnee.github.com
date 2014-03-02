#TOMCAT

## tomcat 설치
### homebrew 이용
brew install tomcat  
왜인지 실패  
![brew_install.png](./tomcat/brew_install.png)

### 직접 설치
1. tomcat download
![tomcat_download.png](./tomcat/tomcat_download.png)
2. tomcat 압축해제후 원하는 위치로 이동
![tomcat_folder.png](./tomcat/tomcat_folder.png)
3. tomcat 설정(path등록) 
![profile_setting.png](./tomcat/profile_setting.png)


## 이클립스 연동

![eclipse_setting_01.png](./tomcat/eclipse_setting_01.png)

![eclipse_setting_02.png](./tomcat/eclipse_setting_02.png)


## 이클립스 연동후 확인 사항
### tomcat [메인 페이지](http://localhost:8080/)가 보이지 않는 경우

Server Locations 항목에서 Use Tomcat installation을 선택
![eclipse_setting.png](./tomcat/eclipse_setting_03.png)
