#GIT

##git 연습 사이트
http://learnbranch.urigit.com/

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

### modified 상태의 파일을 stage하기
새로 추가하는 거랑 명령어가 같음
git add README  

### 파일 무시하기
.gitignore 파일을 만들고 파일안에 무시할 내용을 저장  
==디렉토리 관련 명령어들은 화면에 보이는 것과 실제 사용법이 틀리니 따로 검색 요망==

| 예 | 설명 |
|----|-----|
|# a comment| 이 줄은 무시한다 |
|*.a|확장자가 .a인 파일 무시|
|!lib.a|윗 줄에서 확장자가 .a인 파일은 무시하게 했지만 lib.a는 무시하지 않는다.|
|/TODO|루트 디렉토리에 있는 TODO파일은 무시하고 subdir/TODO처럼 하위디렉토리에 있는 파일은 무시하지 않는다|
|build/|build/ 디렉토리에 있는 모든 파일은 무시한다.|
|doc/*.txt|doc/notes.txt같은 파일은 무시하고 doc/server/arch.txt같은 파일은 무시하지 않는다.|
|doc/**/*.txt|doc 디렉토리 아래의 모든 .txt 파일을 무시한다. **/스타일은 git 1.8.2부터 지원|

### staged와 unstaged 상태의 변경 내용을 보기
git diff  

### staging area에 넣은 파일의 변경 부분 보기
git diff --cached  
git diff --staged  

### 변경사항 커밋하기
편집기가 실행되고 commit 내용을 입력하는 방법.  
git commit  
commit 내용에 diff내용을 포함하는 방법  
git commit -v  
commit 메세지를 인라인으로 포함하는 방법  
git commit -m 'message'  

### Staging Area 생략하기
git commit -a -m 'message'  

### 파일을 삭제하기
git rm {파일명}  

### Stargin Area 에서만 삭제하고 실제 파일을 남겨두기
git rm --cached {filename}  

### 여러 파일이나 폴더를 삭제하기
==하기 명령어들은 화면에 보이는 것과 실제 사용법이 틀리니 따로 검색 요망==  
git rm log/\*.log  
git rm \*~  

### 파일명 변경하기
git mv file_from file_to  


### 커밋 히스토리 조회하기
git log  
git log -p -2  
> -2 는 최근 2개를 의미  
-p 는 각 커밋의 diff 결과를 보여줌  

git log -U1 --word-diff  
>단어 단위로 변경사항 확인  

git log --stat  
>커밋의 통계정보 조회

git log --pretty=online  
git log --pretty=format:"%h -%an, %ar:%s"  
>format의 자세한 옵션은 책을 찾아보자.  

git log --pretty=format:"%h %s" --graph  


|옵션 | 설명|
|-|-|
|-p | 각 커밋에 적용된 패치를 보여준다.|  
|--word-diff | diff 결과를 단어 단위로 보여준다.|  
|--stat | 각 커밋에서 수정된 파일의 통계정보를 보여준다.|  
|--shortstat |  `--stat` 명령의 결과 중에서 수정한 파일, 추가된 줄, 삭제된 줄만 보여준다.|  
|--name-only | 커밋 정보중에서 수정된 파일의 목록만 보여준다.|  
|--name-status  |  수정된 파일의 목록을 보여줄 뿐만 아니라 파일을 추가한 것인지, 수정한 것인지, 삭제한 것인지도 보여준다.|  
|--abbrev-commit | 40자 짜리 SHA-1 체크섬을 전부 보여주는 것이 아니라 처음 몇 자만 보여준다. |
|--relative-date|  정확한 시간을 보여주는 것이 아니라 `2 주전`처럼 상대적인 형식으로 보여준다.|  
|--graph| 브랜치와 머지 히스토리 정보까지 아스키 그래프로 보여준다.|  
|--pretty |   지정한 형식으로 보여준다. 이 옵션에는 oneline, short, full, fuller, format이 있다. format은 원하는 형식으로 출력하고자 할 때 사용한다.|  
|--oneline |  `--pretty=oneline --abbrev-commit` 옵션을 함께 사용한 것과 동일하다.|  

### 조회 제한 조건
git log --since=2.weeks  

| 옵션 | 설명 |
|-|-|
|-(n) |    최근 n 개의 커밋만 조회한다.|
|--since, --after  |  명시한 날짜 이후의 커밋만 검색한다.|
|--until, --before |  명시한 날짜 이전의 커밋만 조회한다.|
|--author    |입력한 저자의 커밋만 보여준다.|
|--committer| 입력한 커미터의 커밋만 보여준다.|


### GUI 도구로 히스토리 시각화
gitk  


## 되돌리기
### 커밋 수정하기
git commit --amend
> git commit -m 'initial commit'
git add forgotten_file
git commit --amend

### 파일 상태를 Unstage로 변경하기
git reset HEAD benchmarks.rb

### modified 파일 되돌리기
git checkout -- benchmarks.rb  

## 리모트 저장소
### 리모트 저장소 확인하기
git remote
>저장소를 clone하면 origin이라는 저장소가 자동으로 등록된다.

git remote -v

### 리모트 저장소 추가하기
git remote add [단축이름] [url]  
> git remote add pb gid://github.com/paulboone/ticgit.git  


### 리모트 저장소를 Pull 하거나 fetch하기
git fetch [remote-name]
> fetch는 모든 데이터를 가져오지만 자동으로 머지해주지 않는다.

git pull [remote-name]
> 가져오고 자동으로 머지한다.

git clone
> 자동으로 로컬의 마스터 브랜치가 리모트 저장소의 마스터 브랜치를 추적하도록 한다.


### 리모트 저장소에 push하기
git push [리모트 저장소 이름] [브랜치 이름]
> git push origin master

