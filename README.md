# git 역할 
- 소스 병합 (merge, rebase)
- 소스 리비전 관리 (reset, commit, branch)
- 소스 릴리즈 (push)
- 소스 변경사항 컴포 (diff, log)

# git 지원
- 윈도우즈
- 맥
- 리눅스
- 유닉스 

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
    - 누구나 쉽게 이해 할 수 있는 git  <https://backlog.com/git-tutorial/kr/>
    - git used <https://github.com/KennethanCeyer/tutorial-git>
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
- 커밋 취소 
```
$ git reeset HEAD^ //마지막 커밋 삭제
$ git reset --hard HEAD // 마지막 커밋 상태로 되돌림. 
$ git resest HEAD * // 스테이징을 언스테이징으로 변경, ref
```

## Branch 
- master 브랜치를 특정 커밋으로 옮기기
```
 git checkout better_branch 
 git merge --strategy=ours master
 git checkout master
 git merge better_branch 
 
```
- 브랜치 목록 
```
$ git branch // 로컬 
$ git branch -r //리모트 
$ git branch -a // 로컬, 리모트 포함된 모든 브랜치 보기 

```

- 브랜치 생성 
```
git branch new master  //master --> new 브랜치 생성
git push origin new  // new 브랜치를 리모트로 보내기 
```

- 브랜치 삭제  
```
git branch -D {삭제할 브랜치 명} // local
git push origin :{the_remote_barnch} // remote
```
- 빈 브랜치 생성 
```
git checkout --orphan {새로운 브랜치명}
git commit -a // 커밋해야 새로운 브랜치 생성 
git checkout -b new-branch // 브랜치 생성과 동시에 체크아웃 

```

- 리모트 브랜치 가져오기 
```
git chekout -t orgin/{가져올 브랜치명} //ref
```

- 브랜치 이름 변경 
```
git branch -m {new name} //ref
```


# conventionalcommits
https://www.conventionalcommits.org/ko/v1.0.0/#%ea%b0%9c%ec%9a%94

## git commit message 
## 커밋메세지 

[기능 추가] feat(수정한 기능 혹은 파일 이름): 커밋 내용
[제거] remove(기능 혹은 파일 이름): 커밋 내용
[버그픽스] fix(기능 혹은 파일 이름): 커밋 내용


[제거] remove(): 커밋 내용

remove(commbot-head) : >>>>>>> Stashed changes  삭제 

ex)
feat(수정한 기능 혹은 파일 이름): 커밋 내용
feat(header): 마크업 등록
feat(수정한 기능 혹은 파일 이름): 커밋 내용
