# git 명령어 모음 

## 구조 
스테이징 -> 커밋 -> 원격저장소 
1. git add {파일명}  -  스테이징 상태로 
2. git commit 으로 스테이징 상태에 있는 모든 변경사항을 커밋한다. 여기까지 로컬작업 
3. git push 로 커밋된 저장소를 원격 저장소로 push. 


## 기본명령어

- 저장소 생성 
```
 git init 
```

- 원격 저장소로부터 복제 
```
 git clone {url}
```

- 변경사항 체크 
```
  git status 
```

- 특정 파일 스테이징 
```
  git add {파일명}
```

- 변경된 모든 파일 스테이징   
```
 git add *
```

- 커밋 
```
  git commit -m  "{변경 내용}"
```

- 원격으로 보내기 
```
  git push origin master
```
- 원격저장소 추가 
```
 git remote add origin {원격서버주소}
```

- 참고 
    - git download <https://code.google.com/archive/p/git-osx-installer/downloads>
    - git cheat sheet <http://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf>
    - git guide Ko <http://rogerdudler.github.io/git-guide/index.ko.html>
    - Github - fork <https://code.google.com/archive/p/git-osx-installer/downloads>


## Commit 
- 커밋 합치기 
```
git rebase -i HEAD~4 //  최신 4개의 커밋을 하나로 합치기 
```

- 커밋 메세지 수정
```
$ git commit --amed // 마지막 커밋메세지 수정 (ref)
```

- 간단한 커밋 방법
```
$ git add {변경한 파일명}
$ git commit -m "{변경 내용}"
```
- 커밋 이력 확인 
```
$ git log // 모든 커밋로그 확인 
$ git log -3 //최근 3개 커밋로그 확인 
$ git log --pretty=oneline // 각 커밋을 한 줄로 표시 
```
