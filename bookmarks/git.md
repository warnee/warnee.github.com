#GIT

##git 설정

###git 설정파일
/etc/gitconfig 모든 사용자, 모든 저장소에 적용  
~/.gitconfig 해당 사용자에 적용  
.git/config 해당 저장소만 적용  

우선순위 .git/config > ~/.gitconfig > /etc/gitconfig

### 사용자 정보 설정
하기 정보는 한번만 설정하면 됨  
git config --global user.name "Taewon Jung"  
git config --global user.email darkwarnee@gmail.com

### 편집기 설정
git config --global core.editor emacs  
git config --global core.editor vim  
입맛에 맞게 골라 쓰기

### merge tool
git config --global merge.tool vimdiff

### 설정확인
git config --list
### 특정 키 확인
git config user.name

### 도움말
git help config

## git 사용
### 저장소 만들기
git init 저장소 만들기  
git add *.* 모든 파일 추가  
git add README 파일 추가  
git commit -m 'initial project version'

### 저장소 복사
grit이라는 폴더로 복사  
git clone git://github.com/schacon/grit.git  
mygrit이라는 폴더로 복사  
git clone git://github.com/schacon/grit.git mygrit  


### 파일 상태 확인
git status

### 파일을 새로 추적하기(파일 추가)
git add README

### modified 상태의 파일 추적
새로 추가하는 거랑 명령어가 같음
git add README  

