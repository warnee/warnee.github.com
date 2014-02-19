#maven

##설치
brew install maven

##기타
###이클립스 라이브러리의 소스 추가
mvn eclipse:eclipse -DdownloadSources -DdownloadJavadocs 

### 이클립스 클린
mvn clean eclipse:eclipse

### 이클립스 클린 인스톨
mvn clean install