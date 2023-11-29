# Git
(버전을 통해, 분산된 방식으로) 코드를 관리하는 도구
+ 백업도구
+ 협업도구
+ 배포도구


## Git?
* SCM(Source Code Management) : 코드 관리 도구
* VCS(Version Control System) : 버전 관리 도구(시스템)
* DVCS(Distributed VCS) : 분산형 버전 관리 시스템(도구)

## I. 버전 관리 Git 명령어
### (1)`git init`
- Git은 폴더(디렉토리) 단위로 코드를 관리
- Git 프로젝트 시작 전에는 해당 폴더(디렉토리)를 생성
- 결과: 프로젝트 폴더 내에 `.git` 폴더를 생성 : Git이 관리와 관련된 파일

### (2)`git status` : git 상태 출력

#### 최초 상태
```bash
On branch master -> master라는 branch에 있음

No commits yet -> commit이 아직 없음

nothing to commit (create/copy files and use "git add"to track) 
-> commit 할것도 없음

```

#### `a.txt` 파일 생성 후
```bash
On branch master

No commits yet

Untracked files: -> 추적되지 않은 파일 있음
  (use "git add <file>..." to include in what will be committed)
        a.txt
    -> commit 될 것에 포함 시키고 싶으면 git add <파일명> 을 사용해
nothing added to commit but untracked files present (use "git add" to track)
-> commit 할 것은 없는데, 추적되지 않은 파일은 있음 (추적하고 싶으면 git add)
```
#### `git add a.txt` 입력 후
```bash
...

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt
```
#### `git commit` 후
```bash
On branch master
nothing to commit, working tree clean
```

### (3)`git add [파일/폴더]`
- commit을 하기 위한 stage(== 버전을 생성하기 위한 준비단계)
- `git add .` : 현재 폴더의 모든 변경 사항 stage

### (4)`git commit -m "메시지`
>commit == 버전을 생성 == 현재상태의 스냅샷 촬영
#### 최초 commit 시
```bash
Author identity unknown -> 작자 미상

*** Please tell me who you are. -> 너가 누군지 알려줘

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity. -> 너의 계정의 기본 신원을 설정하기 위해
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'USER@DESKTOP-VLD6L4G.(none)')


```
#### `git config` 설정 후(`vim` 에디터 창)

```bash
# Please enter the commit message for your changes.
-> 변경사항에 대한 commit message를 입력해주세요.
# Lines starting with '#' will be ignored, and an empty message aborts the
commit.
-> #로 시작하는 라인은 무시됩니다. 아무것도 없는 메시지는 종료됩니다.
# On branch master
#
# Initial commit
#
# Changes to be committed:
# new file: test.txt
```

### (5)`git config`: Git 관련 설정

```bash
git config --global user.email "내 이메일" : global(전역으로) user의 email을 설정
git config --global user.email : 설정값 확인

```

### (6) `git log` :Commit 목록

---
## II. 백업 Git 명령어
### (7) `git remote`
- 원격 저장소(Remote Repository)에 대한 정보
- `git remote add` : 원격 저장소 추가
    - `git remote add [저장소이름][저장소주소]`
    - `git remote add origin https://github.com/xxx`

```bash
ex)
git remote add origin https://github.com/hkeryfonttlxisdrlw/basic_git
git에게 원격저장소(remote) 추가(add)를 명령
저장소이름: origin
저장소주소: https://github.com/hkeryfonttlxisdrlw/basic_git

```


### (8) `git push` : 원격 저장소에 프로젝트 업로드
- `git push [저장소이름] [브랜치이름]`
- `git push origin `
