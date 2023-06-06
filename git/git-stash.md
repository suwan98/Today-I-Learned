<h1>Git stash</h1>

<br/>

> **Stahsh**

**파일의 변경 내용을 일시적으로 기록해두는 영역**이다 <br />
아직 마무리 하지 않은 작업을 스택에 **잠시 저장**할 수 있도록 한다.
이를 통해 아직 완료하지 않은 일을 **commit**하지 않고 나중에 다시 꺼내와 마무리 할 수 있다

<br/>

> **Git Stash 예시**

- 파일을 수정하고 있는 정웨 다른 brach로 이동해야 하는 상황이 생겼다
- master 브랜치에서 작업해야 하는데, 다른 브랜치에서 모르고 작업했을 때 stash로 저장하고 master 브랜치로 넘어와 임시로 저장된 작업내용을 적용해주면 유용하게 쓰일 수 있다

<br />

<hr />

<h2>✍️ stash 저장하기</h2>

<br />

```bash
# 현재 작업 수정 내역을 임시저장소에 저장한다.
$ git stash

# 설명도 함께 동봉할 수 도 있다.
$ git stash save "설명"
```

<br />

 <h2>✍️ stash 목록 확인하기 </h2> 

 `git stash list`

 ```bash
# stash들의 목록을 확인할 수 있다
$ git stash list
 ```

<br />


 <h2>✍️ stash 적용하기 </h2> 

`git stash apply`
 
```bash
# 가장 최근 stash를 가져와 적용한다
$ git stash apply
# stash 이름에 해당 하는 stash를 적용한다
$ git stahsh apply "stash 이름"
 ```
 
 그러나 위의 명령어로는 Staged 상태 였던 파일을 자동으로 다시 Staged 상태로 만들어 주진 않는다. <br/>
 `-index`옵션을 주어야 Staged 된 상태까지 복원한다. <br/>
이를 통해 원래 작업하던 파일의 상태로 돌아 올 수 있다
```bash
# Staged 상태까지 저장
$ git stash apply --index
```

<br />

 <h2>✍️ stash 삭제하기 </h2> 

`git stash drop` <br/>

`apply` 옵션은 단순히 stash를 적용하는 것으로 <br />
해당 stash는 여전히 스택에 남아있다. <br />
스택에 남아 있는 stash는 위의 명령어를 사용하여 제거할 수 있다
```bash
# 가장 최근의 stash를 제거한다.
$ git stash drop
# stash 이름에 해당하는 stash를 지정하여 제거한다
$ git stash drop "삭제하려고 하는 stash 이름"
```



<br />

 <h2>✍️ stash 되돌리기 </h2> 

 `git stash show -p | git apply -R`

 실수로 잘못 stash가 적용한 것을 **되돌리고 싶으면** 사용한다

```bash
# 가장 최근의 stash를 사용해 패치를 만들고 그것을 거꾸로 적용한다
$ git stash show -p | git apply -R
# stash 이름에 해당하는 stash를 이용하여 그것을 거꾸로 적용한다
$ git stash show -p "적용하고자 하는 stash 이름" | git apply -R
```