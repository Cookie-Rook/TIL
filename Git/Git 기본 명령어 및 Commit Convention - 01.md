# Git 기본 명령어 및 Commit Convention

### Contents

1. Git 설치
2. Git 기본 명령어 (1) : init, clone, remote, add, status, commit, push
3. Commit convention
4. 참고자료

<br>

### 1. Git 설치

- Git 설치
  <br> - 홈페이지()에서 최신 버전을 기준으로 맞는 OS에 따라 설치.
  <br> - 설치시 결정해야 할 옵션이 많으니 다음의 사이트를 참고 ()
  <br> - 변화 없이 기본 옵션으로도 설치가 가능하다.
  <br><br>
- 추가정보
  <br> - Window powershell 환경에서 Linux 명령어 사용 `$wls`
  <br> - Window powershell 환경에서 Git 설치 확인 `$git version`
  <br> - git repository 최초 연결을 위한 config 파일 연결

  ```
  $git config --global user.name "<사용자이름>"
  $git config --global user.email <사용자이메일>
  ```

<br>

### 2. Git 기본 명령어 (1)

#### 2-1. Git 시작하기

- init <br> 현재 폴더를 git의 로컬저장소로 사용. <br> ".git" 파일 생성 <br>

  ```
  git init
  ```

- clone <br> 현재 폴더에 git 저장소의 내용을 복사하기 <br>
  git_url : 복사할 원격 저장소의 위치 <br>

  ```
  git clone <git_url>
  ```

- remote <br>
  원격 저장소와 로컬 저장소를 연결 <br>
  remote_name : remote repository의 이름 <br>
  git_url : 연결할 원격 저장소의 위치 <br>
  ```
  git remote add <remote_name> <git_url>
  ```
  <br>

#### 2-2. Github 로컬저장소 변경하기

- add <br>
  `file_name` : 수정된 특정 파일을 staging 영역에 추가 <br>
  `.` : 현재 폴더의 변경 사항을 staging 영역에 추가 <br>
  `-A` : 모든 수정된 파일을 staging 영역에 추가 <br>

  ```
  git add <file_name>
  git add .
  git add -A
  ```

- status <br>
  staging 영역에 추가된 사항 확인 <br>
  ```
  git status
  ```
  <br>

#### 2-3. Github repository 변경하기

- commit <br>
  연결된 repository에 commit <br>
  `message` : commit 시의 주석으로 작성방안은 [Commit convention](#3.-Commit-Convention) 참조. 2줄 이상으로 작성 가능 <br>

  ```
  git commit -m "<message>"
  ```

- push <br>
  실제 git 저장소에 변경사항 업로드 <br>
  `remote_name` : remote를 통해 저장된 주소 <br>
  `branch` : 변경된 내용을 저장할 git 저장소의 branch. github 기준 main.
  ```
  git push <remote_name> <branch>
  ```
    <br>
  <br>

### 3. Commit Convention

코드의 수정 내역을 보기 편하기 하기 위한 일종의 규칙. 제목-내용-꼬리말 형태를 따른다. 팀이나 회사 내규에 따라 다르지만, 특정 팀의 규칙을 참조하여 일반적인 형태는 정해져 있다.

```
<Type> : <Subject>

<Body>

<Footer>
```

- `Type` : Commit 종류. 개인적으로 보기 편하기 위해 파일 작성 날짜(Data-code)를 병기할 예정<br>

  - Type 기본 <br>
    **feat** - 기능 추가 <br>
    **fix** - 버그 수정 <br>
    **docs** - 문서 수정 <br>
    **style** - 코드 포맷 수정-주석, 세미콜론 등<br>
    **refactor** - 코드 리팩토링 <br>
    **test** - 테스트 코드 추가 <br>
    **chore** - 빌드 업무 수정 <br>

- `Subject` : Commit 내용 작성. [참고자료](#4-참고자료) 참조.<br>
- `Body` : Commit 세부 내용 작성. 생략 가능.<br>
- `Footer` : Commit과 관련된 이슈 번호 작성. 생략 가능.<br>

<br>

### 4. 참고자료

- 좋은 git commit 메시지를 위한 영어사전<br>
  https://blog.ull.im/engineering/2019/03/10/logs-on-git.html
