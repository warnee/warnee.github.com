#homebrew

##brew 설치
$ ruby -e "$(curl -fsSkL raw.github.com/mxcl/homebrew/go)"


##brew 사용법
### brew를 이용한 설치버전확인
brew info gradle

### 버전 변경
brew switch gradle 1.9

### 버전 저장소 확인
brew search maven

### 원하는 버전 설치
brew install homebrew/versions/maven30

### 원격 저장소의 모든 버전
brew versions gradle

