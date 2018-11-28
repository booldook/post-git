# 각종 설치 및 팁 정리

Git 최초 설정
--

0. git-scm 설치
1. github 에서 new repository 를  실행
2. 작업폴더를 vscode 에서 폴더열기
3. 터미털 창에서 git init
4. .gitignore 파일을 생성
5. (vscode에서 처음 한번만 실행) git config --global user.email "b@g.com"
	-- 5번 과정에서 왼쪽 패널의 파일이 비어있어야 함.(커밋이 완료된 상태)
6. git commit -m "first commit" // ... 의 모두 커밋을 눌러두 된다.
7. git remote add origin https://github.com/booldook/dothome.git
8. git push -u origin master



Git 설정 방법
--
~~~
git init
// git commit -m "first commit"
// 위의 코드보다는 vscode 의 모두 커밋을 실행
git remote add origin https://github.com/booldook/sample.git
// git push -u origin master
// 위의 코드보다는 vscode 의 푸시를 실행
~~~

Firebase 설치
--
firebase PC에서 환경설정
1. node.js 설치 (npm 설치) - 1번만
2. 터미널에서 npm install -g firebase-tools 실행 - 1번만
3. 터미널에서 firebase login - 1번만
4. 폴더 생성하고, vscode 에서 폴더 열고, vscode 터미널을 켠다.
5. firebase 콘솔(웹)에서 프로젝트 생성
6. 예) D:\test\ --> firebase init 실행
7. 설치가 완료되면 firebase serve / firebase deploy



# Firebase 설치
### nodejs 설치
~~~
node -v
~~~
---
### firebase cli 설치
~~~
npm install -g firebase-tools
~~~
---
### firebase Login
~~~
firebase login
firebase list
~~~
---
### firebase 프로젝트 만들기
개발폴더에 firebase 프로젝트폴더 생성후 (ex: firebasememo)
해당폴더로 이동후
~~~
firebase init
-> database선택
-> database.rule.json
-> public 폴더 사용
-> index.html 사용
~~~
---
### firebase 실행
~~~
firebase serve
~~~
---
### firebase 배포
~~~
firebase deploy
~~~
---


## 우리가 배운 개발 환경
```
html5/css3/Javascript ES5/jQuery + Ajax + Firebase
```
---
## 실무에서 마주하게 될 개발 환경

```
가. PHP/ASPX/JSP 개발환경 - 회사마다 즐겨 사용하는 Framework에서 작업 (80%~)
  예) codeIgniter(php), Yii(php) ...
나. FrontEnd 개발 환경 - node.js(npm)
  예) Webpack Babel/React/React Reduce/Angular/Vue/Ionic/....
```
---


# GIT 팁 모음
### 20개 내외의 명령어로 Git 사용하기
```sh
git help everyday
```

### Git과 함께 제공되는 유용한 가이드라인 보기
```sh
git help -g
```

### 내용으로 변경사항 검색
```sh
git log -S'<a term in the source>'
```

### 원격지 동기화 및 로컬 변경사항 덮어쓰기
```sh
git fetch origin && git reset --hard origin/master && git clean -f -d
```

### 특정 커밋까지의 모든 파일 나열하기
```sh
git ls-tree --name-only -r <commit-ish>
```

### 첫 번째 커밋 초기화
```sh
git update-ref -d HEAD
```

### 충돌된 모든 파일 나열하기
```sh
git diff --name-only --diff-filter=U
```

### 특정 커밋에서 변경된 모든 파일 나열하기
```sh
git diff-tree --no-commit-id --name-only -r <commit-ish>
```

### 마지막 커밋 이후로 스테이징되지 않은 변경사항 보기
```sh
git diff
```

### 커밋을 하기 위해 스테이징된 변경사항 보기
```sh
git diff --cached
```


__다른 방법:__
```sh
git diff --staged
```

### 스테이징된 변경사항과 스테이징되지 않은 변경사항 모두 보기
```sh
git diff HEAD
```

### 이미 마스터 브랜치에 머지된 모든 브랜치 나열하기
```sh
git branch --merged master
```

### 이전 브랜치로 전환하기
```sh
git checkout -
```


__다른 방법:__
```sh
git checkout @{-1}
```

### 이미 마스터 브랜치에 머지된 모든 브랜치들 삭제하기
```sh
git branch --merged master | grep -v '^\*' | xargs -n 1 git branch -d
```


__다른 방법:__
```sh
git branch --merged master | grep -v '^\*\|  master' | xargs -n 1 git branch -d # will not delete master if master is not checked out
```

### 모든 브랜치들 및 그 브랜치들의 업스트림과 마지막 커밋 나열하기
```sh
git branch -vv
```

### 업스트림 브랜치 설정 (트래킹)
```sh
git branch -u origin/mybranch
```

### 로컬 브랜치 삭제
```sh
git branch -d <local_branchname>
```

### 원격 브랜치 삭제
```sh
git push origin --delete <remote_branchname>
```


__다른 방법:__
```sh
git push origin :<remote_branchname>
```

### 로컬 태그 삭제
```sh
git tag -d <tag-name>
```

### 원격 태그 삭제
```sh
git push origin :refs/tags/<tag-name>
```

### 로컬 변경사항을 헤드의 마지막 내용으로 되돌리기
```sh
git checkout -- <file_name>
```

### Revert: 새로운 커밋을 생성하면서 커밋 되돌리기
```sh
git revert <commit-ish>
```

### Reset: 커밋 제거 (프라이빗 브랜치에서만 사용하길 권고)
```sh
git reset <commit-ish>
```

### 이전 커밋 메시지 변경
```sh
git commit -v --amend
```

### 브랜치의 커밋중 업스트림에 머지되지 않은 커밋 히스토리 보기
```sh
git cherry -v master
```

### Author 수정하기
```sh
git commit --amend --author='Author Name <email@address.com>'
```

### 글로벌 설정에서 변경된 author로 author 재설정하기
```sh
git commit --amend --reset-author --no-edit
```

### 원격지 URL 변경하기
```sh
git remote set-url origin <URL>
```

### 모든 원격지 레퍼런스 리스트 나열하기
```sh
git remote
```


__다른 방법:__
```sh
git remote show
```

### 모든 로컬 및 원격지 브랜치 나열하기
```sh
git branch -a
```

### 원격지 브랜치만 나열하기
```sh
git branch -r
```

### 파일 변경사항의 전체가 아닌 일부만 스테이징하기
```sh
git add -p
```

### Git 배시 자동완성 사용하기
```sh
curl http://git.io/vfhol > ~/.git-completion.bash && echo '[ -f ~/.git-completion.bash ] && . ~/.git-completion.bash' >> ~/.bashrc
```

### 2주 전부터 현재까지의 변경사항 보기
```sh
git log --no-merges --raw --since='2 weeks ago'
```


__다른 방법:__
```sh
git whatchanged --since='2 weeks ago'
```

### 마스터로부터 포크한 이후에 생성된 모든 커밋 보기
```sh
git log --no-merges --stat --reverse master..
```

### cherry-pick을 사용해 브랜치간 커밋 가져오기
```sh
git checkout <branch-name> && git cherry-pick <commit-ish>
```

### 해당 커밋 해시를 가지고 있는 브랜치들 검색하기
```sh
git branch -a --contains <commit-ish>
```


__다른 방법:__
```sh
git branch --contains <commit-ish>
```

### Git 명령어 별칭 지정
```sh
git config --global alias.<handle> <command> 
git config --global alias.st status
```

### 커밋하지 않은 트래킹된 파일들의 상태 저장하기
```sh
git stash
```


__다른 방법:__
```sh
git stash save
```

### 스테이징되지 않은 변경사항들의 현재 상태를 트래킹된 파일로 저장하기
```sh
git stash -k
```


__다른 방법:__
```sh
git stash --keep-index
```


```sh
git stash save --keep-index
```

### 트래킹되지 않은 파일들까지 모두 포함해 현재 상태 저장하기
```sh
git stash -u
```


__다른 방법:__
```sh
git stash save -u
```


```sh
git stash save --include-untracked
```

### 현재 상태를 메시지와 함께 저장하기
```sh
git stash save <message>
```

### 모든 무시된 파일, 트래킹되지 않은 파일, 트래킹된 파일들의 현재 상태 저장하기
```sh
git stash -a
```


__다른 방법:__
```sh
git stash --all
```


```sh
git stash save --all
```

### 저장된 모든 스태시 리스트 나열하기
```sh
git stash list
```

### 스태시 리스트에서 삭제하지 않고 스태시 적용하기
```sh
git stash apply <stash@{n}>
```

### 마지막으로 저장된 스태시 상태를 적용하고 스태시 리스트에서 삭제하기
```sh
git stash pop
```


__다른 방법:__
```sh
git stash apply stash@{0} && git stash drop stash@{0}
```

### 저장된 모든 스태시 삭제하기
```sh
git stash clear
```


__다른 방법:__
```sh
git stash drop <stash@{n}>
```

### 스태시로부터 단일 파일 가져오기
```sh
git checkout <stash@{n}> -- <file_path>
```


__다른 방법:__
```sh
git checkout stash@{0} -- <file_path>
```

### 트래킹된 파일들 모두 보기
```sh
git ls-files -t
```

### 트래킹되지 않은 파일들 모두 보기
```sh
git ls-files --others
```

### 무시된 파일들 모두 보기
```sh
git ls-files --others -i --exclude-standard
```

### 저장소에 새로운 워킹 트리 생성하기 (git 2.5)
```sh
git worktree add -b <branch-name> <path> <start-point>
```

### HEAD로부터 새로운 워킹 트리 생성하기
```sh
git worktree add --detach <path> HEAD
```

### 파일을 삭제하지 않고 언트래킹하기
```sh
git rm --cached <file_path>
```


__다른 방법:__
```sh
git rm --cached -r <directory_path>
```

### 트래킹되지 않은 파일/디렉토리를 실제로 삭제하기 전에 어떤 파일/디렉토리가 삭제되는지 테스트 해보기
```sh
git clean -n
```

### 트래킹되지 않은 파일들 강제로 삭제하기
```sh
git clean -f
```

### 트래킹되지 않은 디렉토리 강제로 삭제하기
```sh
git clean -f -d
```


__다른 방법:__
```sh
git clean -df
```

### 모든 서브 모듈 업데이트하기
```sh
git submodule foreach git pull
```


__다른 방법:__
```sh
git submodule update --init --recursive
```


```sh
git submodule update --remote
```

### 현재 브랜치에서 아직 마스터에 머지되지 않은 모든 커밋들 보기
```sh
git cherry -v master
```


__다른 방법:__
```sh
git cherry -v master <branch-to-be-merged>
```

### 브랜치명 수정하기
```sh
git branch -m <new-branch-name>
```


__다른 방법:__
```sh
git branch -m [<old-branch-name>] <new-branch-name>
```

### 'feature' 브랜치를 마스터에 리베이스한 후 마스터에 머지하기
```sh
git rebase master feature && git checkout master && git merge -
```

### 마스터 브랜치 아카이브
```sh
git archive master --format=zip --output=master.zip
```

### 커밋 메시지는 변경하지 않고 이전 커밋 변경하기
```sh
git add --all && git commit --amend --no-edit
```

### 원격지에서 삭제된 원격 브랜치 레퍼런스 제거하기
```sh
git fetch -p
```


__다른 방법:__
```sh
git remote prune origin
```

### 첫 리비전의 커밋 해시값 가져오기
```sh
 git rev-list --reverse HEAD | head -1
```


__다른 방법:__
```sh
git rev-list --max-parents=0 HEAD
```


```sh
git log --pretty=oneline | tail -1 | cut -c 1-40
```


```sh
git log --pretty=oneline --reverse | head -1 | cut -c 1-40
```

### 버전 트리 시각화
```sh
git log --pretty=oneline --graph --decorate --all
```


__다른 방법:__
```sh
gitk --all
```

### 트래킹된 하위폴더를 gh-pages 브랜치로 배포하기
```sh
git subtree push --prefix subfolder_name origin gh-pages
```

### subtree를 사용해 저장소에 프로젝트 추가하기
```sh
git subtree add --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

### subtree를 사용해 관련된 프로젝트의 최신 변경사항을 저장소로 가져오기
```sh
git subtree pull --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

### 브랜치를 히스토리와 함께 파일로 추출하기
```sh
git bundle create <file> <branch-name>
```

### 번들 가져오기
```sh
git clone repo.bundle <repo-dir> -b <branch-name>
```

### 현재 브랜치명 가져오기
```sh
git rev-parse --abbrev-ref HEAD
```

### 커밋시 파일 무시하기 (예를 들어, Changelog 파일)
```sh
git update-index --assume-unchanged Changelog; git commit -a; git update-index --no-assume-unchanged Changelog
```

### 리베이스 전에 변경사항 스태시하기
```sh
git rebase --autostash
```

### ID로 풀 리퀘스트를 로컬 저장소로 가져오기
```sh
git fetch origin pull/<id>/head:<branch-name>
```


__다른 방법:__
```sh
git pull origin pull/<id>/head:<branch-name>
```

### 현재 브랜치의 가장 최근 태그 보기
```sh
git describe --tags --abbrev=0
```

### diff 워드 단위로 보기
```sh
git diff --word-diff
```

### diff 도구를 사용해 변경사항 보기
```sh
git difftool -t <commit1> <commit2> <path>
```

### 트래킹된 파일의 변경사항 무시하기
```sh
git update-index --assume-unchanged <file_name>
```

### assume-unchanged 되돌리기
```sh
git update-index --no-assume-unchanged <file_name>
```

### `.gitignore`에 명시된 파일들 삭제하기
```sh
// 원격 저장소와 로컬 저장소에 있는 파일을 삭제한다.
$ git rm [File Name]

//원격 저장소에 있는 파일을 삭제한다. 로컬 저장소에 있는 파일은 삭제하지 않는다.
$ git rm --cached [File Name]
```

### 삭제된 파일 복구하기
```sh
git checkout <deleting_commit>^ -- <file_path>
```

### 특정 커밋으로의 파일로 복구하기
```sh
git checkout <commit-ish> -- <file_path>
```

### pull시 머지하는 대신 항상 리베이스 하기
```sh
git config --global pull.rebase true
```


__다른 방법:__
```sh
#git < 1.7.9
git config --global branch.autosetuprebase always
```

### 모든 별칭과 설정값들 나열하기
```sh
git config --list
```

### 대소문자 구별 활성화
```sh
git config --global core.ignorecase false
```

### 커스텀 에디터 추가하기
```sh
git config --global core.editor '$EDITOR'
```

### 오타 자동 수정 활성화
```sh
git config --global help.autocorrect 1
```

### 변경사항이 어떤 릴리즈에 속하는지 확인하기
```sh
git name-rev --name-only <SHA-1>
```

### 명령어 테스트 해보기 (dry-run 플래그를 지원하는 모든 명령어에서 가능)
```sh
git clean -fd --dry-run
```

### 커밋이 이전 커밋의 수정 버전임을 표시하기
```sh
git commit --fixup <SHA-1>
```

### fixup 커밋을 일반 커밋으로 스쿼시하기
```sh
git rebase -i --autosquash
```

### 커밋시 스테이징된 파일들 스킵하기
```sh
git commit --only <file_path>
```

### 대화형으로 스테이징하기
```sh
git add -i
```

### 무시된 파일들 나열하기
```sh
git check-ignore *
```

### 무시된 파일들 상태 출력
```sh
git status --ignored
```

### Branch2에는 없고 Branch1에만 있는 커밋들 나열하기
```sh
git log Branch1 ^Branch2
```

### 마지막 n개의 커밋 나열하기
```sh
git log -<n>
```


__다른 방법:__
```sh
git log -n <n>
```

### 이전에 충돌을 해결했던 방법을 기록하고 재사용하기
```sh
git config --global rerere.enabled 1
```

### 모든 충돌된 파일들 에디터로 열기
```sh
git diff --name-only | uniq | xargs $EDITOR
```

### unpacked 오브젝트의 갯수와 디스크 사용량 보기
```sh
git count-objects --human-readable
```

### 오브젝트 데이터베이스에서 도달할 수 없는 오브젝트들 제거하기
```sh
git gc --prune=now --aggressive
```

### gitweb으로 워킹 디렉토리 탐색하기
```sh
git instaweb [--local] [--httpd=<httpd>] [--port=<port>] [--browser=<browser>]
```

### 커밋 로그에서 GPG 시그니쳐 보기
```sh
git log --show-signature
```

### 글로벌 설정에서 엔트리 제거하기
```sh
git config --global --unset <entry-name>
```

### 히스토리가 없는 새로운 브랜치로 체크아웃하기
```sh
git checkout --orphan <branch_name>
```

### 다른 브랜치에서 파일내용 가져오기
```sh
git show <branch_name>:<file_name>
```

### 루트 커밋과 머지 커밋만 나열하기
```sh
git log --first-parent
```

### 대화형 리베이스로 이전 두 커밋 수정하기
```sh
git rebase --interactive HEAD~2
```

### 작업중인 브랜치들 모두 나열하기
```sh
git checkout master && git branch --no-merged
```

### 이진 탐색으로 좋은/안좋은 커밋 검색하기
```sh
git bisect start                    # Search start 
git bisect bad                      # Set point to bad commit 
git bisect good v2.6.13-rc2         # Set point to good commit|tag 
git bisect bad                      # Say current state is bad 
git bisect good                     # Say current state is good 
git bisect reset                    # Finish search 

```

### pre-commit과 commit-msg 깃 후킹 우회하기
```sh
git commit --no-verify
```

### 특정 파일에 대한 커밋과 변경사항 나열하기 (이름이 바뀐 파일도 추적)
```sh
git log --follow -p -- <file_path>
```

### 단일 브랜치 클론
```sh
git clone -b <branch-name> --single-branch https://github.com/user/repo.git
```

### 새로운 브랜치 생성과 동시에 스위칭
```sh
git checkout -b <branch-name>
```


__다른 방법:__
```sh
git branch <branch-name> && git checkout <branch-name>
```

### 커밋시 파일 모드 변경 무시
```sh
git config core.fileMode false
```

### Git 터미널 색상 출력 비활성화
```sh
git config --global color.ui false
```

### 특정 명령어에 대한 색상 설정 지정하기
```sh
git config --global <specific command e.g branch, diff> <true, false or always>
```

### 모든 로컬 브랜치를 최근 커밋 날짜를 기준으로 정렬해 나열하기
```sh
git for-each-ref --sort=-committerdate --format='%(refname:short)' refs/heads/
```

### 트래킹된 파일에서 패턴(정규식이나 문자열)에 매칭되는 라인 검색
```sh
git grep --heading --line-number 'foo bar'
```

### 저장소의 얕은 카피 버전 클론하기
```sh
git clone https://github.com/user/repo.git --depth 1
```

### 모든 브랜치에서 주어진 텍스트로 커밋 로그 검색하기
```sh
git log --all --grep='<given-text>'
```

### 브랜치의 첫 커밋 가져오기 (마스터 브랜치로부터 시작된)
```sh
git log master..<branch-name> --oneline | tail -1
```

### 스테이징된 파일들 언스테이징하기
```sh
git reset HEAD <file-name>
```

### 원격 저장소에 강제 푸시하기
```sh
git push -f <remote-name> <branch-name>
```

### 저장소명 추가하기
```sh
git remote add <remote-nickname> <remote-url>
```

### 주어진 파일의 각 라인별 author, 시간 그리고 최종 리비전명 보기
```sh
git blame <file-name>
```

### Author와 제목으로 커밋 그룹핑하기
```sh
git shortlog
```

### 다른 사람이 작업한 내용을 덮어쓰지 않고 강제 푸시하기
```sh
git push --force-with-lease <remote-name> <branch-name>
```

### 특정 author가 기여한 라인수 보기
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | gawk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s removed lines: %s total lines: %s
", add, subs, loc }' -
```


__다른 방법:__
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | awk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s, removed lines: %s, total lines: %s
", add, subs, loc }' - # on Mac OSX
```

### Revert: 머지 복구하기
```sh
git revert -m 1 <commit-ish>
```

### 특정 브랜치의 커밋 수 출력하기
```sh
git rev-list --count <branch-name>
```

### 별칭: git undo
```sh
git config --global alias.undo '!f() { git reset --hard $(git rev-parse --abbrev-ref HEAD)@{${1-1}}; }; f'
```

### 오브젝트에 노트(메모) 추가하기
```sh
git notes add -m 'Note on the previous commit....'
```

### 모든 깃 노트 보기
```sh
git log --show-notes='*'
```

### 다른 저장소에 있는 커밋 적용하기
```sh
git --git-dir=<source-dir>/.git format-patch -k -1 --stdout <SHA1> | git am -3 -k
```

### 페치 레퍼런스 지정하기
```sh
git fetch origin master:refs/remotes/origin/mymaster
```

### 두 브랜치의 공통 조상 커밋 찾기
```sh
diff -u <(git rev-list --first-parent BranchA) <(git rev-list --first-parent BranchB) | sed -ne 's/^ //p' | head -1
```

### 푸시되지 않은 커밋들 나열하기
```sh
git log --branches --not --remotes
```


__다른 방법:__
```sh
git log @{u}..
```


```sh
git cherry -v
```

### 공백 변경사항을 제외한 모든 변경사항 추가하기
```sh
git diff --ignore-all-space | git apply --cached
```

### 깃 설정 [로컬/글로벌] 수정하기
```sh
git config [--global] --edit
```

### 특정 구간에서 blame 정보 보기
```sh
git blame -L <start>,<end>
```

### Git의 논리적 변수 보기
```sh
git var -l | <variable>
```

### 패치 파일 미리 포맷팅하기
```sh
git format-patch -M upstream..topic
```

### 저장소명 가져오기
```sh
git rev-parse --show-toplevel
```

### 특정 날짜 구간 사이의 커밋 로그 출력하기
```sh
git log --since='FEB 1 2017' --until='FEB 14 2017'
```

### 로그에서 author 제외하기
```sh
git log --perl-regexp --author='^((?!excluded-author-regex).*)

```

### 브랜치의 수정사항 요약하기
```sh
git request-pull v1.0 https://git.ko.xz/project master:for-linus
```

### 원격 저장소의 모든 레퍼런스 나열하기
```sh
git ls-remote git://git.kernel.org/pub/scm/git/git.git
```

### 트래킹되지 않은 파일들 백업하기
```sh
git ls-files --others -i --exclude-standard | xargs zip untracked.zip
```

### 모든 git 명령어 별칭 나열하기
```sh
git config -l | grep alias | sed 's/^alias\.//g'
```


__다른 방법:__
```sh
git config -l | grep alias | cut -d '.' -f 2
```

### git 상태 간략하게 보기
```sh
git status --short --branch
```

### 하루 전의 커밋으로 체크아웃하기
```sh
git checkout master@{yesterday}
```

# GIT 주요 명령어
---
#### git-usage
자주 사용하는 깃 명령어 모음 


#### 구조 

코드는 아래 세 단계에 걸쳐 저장된다.

스테이징 -> 커밋 -> 원격저장소

1. git add {파일명} 으로 파일을 스테이징 상태에 넣는다.
2. git commit 으로 스테이징 상태에 있는 모든 변경사항을 커밋한다. 여기까지가 로컬에서의 작업
3. git push 로 커밋된 저장소를 원격 저장소로 밀어넣는다.


#### 기본 명령어

저장소 생성

```
git init
```

원격 저장소로부터 복제 

```
git clone {url}
```

변경 사항 체크

```
git status // 
```

특정 파일 스테이징

```
git add {파일명} 
```

변경된 모든 파일 스테이징

```
git add * 
```

커밋

```
git commit -m “{변경 내용}” 
```

원격으로 보내기

```
git push origin master 
```

원격저장소 추가

```
git remote add origin {원격서버주소} 
```

참고 페이지

- download(osx): http://code.google.com/p/git-osx-installer/downloads/list
- download(windows): http://git-scm.com/download/win
- 설치 메뉴얼: http://blog.outsider.ne.kr/389
- 사용 메뉴얼:http://dogfeet.github.io/articles/2012/how-to-github.html
- git 간편 안내서: http://rogerdudler.github.com/git-guide/index.ko.html
- 한장으로 핵심 기능만: http://rogerdudler.github.com/git-guide/files/git_cheat_sheet.pdf


#### Commit

커밋 합치기

```
git rebase -i HEAD~4 // 최신 4개의 커밋을 하나로 합치기
```

커밋 메세지 수성

```
$ git commit --amend // 마지막 커밋메세지 수정(ref)
```

간단한 commit방법

```
$ git add {변경한 파일병}
$ git commit -m “{변경 내용}"
```

커밋 이력 확인

```
$ git log // 모든 커밋로그 확인
$ git log -3 // 최근 3개 커밋로그 확인
$ git log --pretty=oneline // 각 커밋을 한 줄로 표시
```

커밋 취소

```
$ git reset HEAD^ // 마지막 커밋 삭제
$ git reset --hard HEAD // 마지막 커밋 상태로 되돌림
$ git reset HEAD * // 스테이징을 언스테이징으로 변경, ref
```


#### Branch

master 브랜치를 특정 커밋으로 옮기기

```
git checkout better_branch
git merge --strategy=ours master    # keep the content of this branch, but record a merge
git checkout master
git merge better_branch            # fast-forward master up to the merge
```

브랜치 목록

```
$ git branch // 로컬
$ git branch -r // 리모트 
$ git branch -a // 로컬, 리모트 포함된 모든 브랜치 보기
```

브랜치 생성

```
git branch new master // master -> new 브랜치 생성
git push origin new // new 브랜치를 리모트로 보내기
```

브랜치 삭제

```
git branch -D {삭제할 브랜치 명} // local
git push origin :{the_remote_branch} // remote
```

빈 브랜치 생성

```
$ git checkout --orphan {새로운 브랜치 명}
$ git commit -a // 커밋해야 새로운 브랜치 생성됨
$ git checkout -b new-branch // 브랜치 생성과 동시에 체크아웃
```

리모트 브랜치 가져오기

```
$ git checkout -t origin/{가져올 브랜치명} // ref
```

브랜치 이름 변경

```
$ git branch -m {new name} // ref
```


#### Tag


태그 생성

```
git tag -a {tag name} -m {tag message} {commit hash}
git tag {tag name} {tag name} -f -m "{new message}" // Edit tag message
```

태그 삭제

```
git tag -d {tag name}
git push origin :tags/{tag name} // remote
```

태그 푸시

```
git push origin --tags
git push origin {tag name}
git push --tags
```


#### 기타 

파일 삭제

```
git rm --cached --ignore-unmatch [삭제할 파일명]
```

히스토리 삭제

- 목적: 패스워드, 아이디 같은 비공개 정보가 담긴 파일을 실수로 올렸을 때 삭제하는 방법이다. (history에서도 해당 파일만 삭제)

```
$ git clone [url] # 소스 다운로드
$ cd [foler_name] # 해당 폴더 이동
$ git filter-branch --index-filter 'git rm --cached --ignore-unmatch [삭제할 파일명]' --prune-empty -- --all # 모든 히스토리에서 해당 파일 삭제
$ git push origin master --force # 서버로 전송
```

히스토리에서 폴더 삭제:

```
git filter-branch --tree-filter 'rm -rf vendor/gems' HEAD
```

리모트 주소 추가하여 로컬에 싱크하기

```
$ git remote add upstream {리모트 주소}
$ git pull upstream {브랜치명}
```

최적화

```
$ git gc
$ git gc --aggressive
```

#### 서버 설정

강제 푸시 설정

```
git config receive.denynonfastforwards false
```

#### Alias

~/.gitconfig 파일을 설정하여 깃 명령어의 앨리어스를 지정할 수 있다.

~/.gitconfig > alias 부분:

```

[alias]
  br = branch
  co = checkout
  rb = rebase
  st = status
  cm = commit
  pl = pull
  ps = push
  lg = log --graph --abbrev-commit --decorate --format=format:'%C(cyan)%h%C(reset) - %C(green)(%ar)%C(reset)  %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(yellow)%d%C(reset)' --all
  ad = add
  tg = tag
  df = diff 
```



