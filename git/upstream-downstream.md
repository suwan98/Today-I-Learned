# UpStream 과 DownStream? 🤔

<br/>

> ## UpStream의 정의 ✍️

`Git 원격 저장소(remote repository)를 가리키는 말`로, <Br/>다른 개발자나 협업자들과의 작업을 **공유하고 관리**하는 **저장소**
<br />

`Git`에서 upstream 저장소는 `fork`한 저장소의 원본저장소를 뜻하는데 <br />
`pull request(PR)` 등을 이용해 원본 저장소에 **반영**할 수 있는 **저장소**를 의미한다

<br/>
<hr />


> ## UpStream과 DownStream의 관계 ✍️

<br />

**upstream** => 내가 `fork`한 **원본 저장소** <br/>
**downstream** => 나와 같은 엔드 유저가 `fork`한 **나의 저장소** <br />


<Br />

upstream 과 downstream은 **상대적인 개념** 이다 <br/>
원본 저장소로 부터 `fork`하여 만든 저장소가 **downstream** 이 되고 <br />
그 원본 저장소가 **upstream**이 된다 <br />
즉, 어떤 저장소가 **upstream**이 되기 위해선, <br /> 다른 저장소가 **그 upstream**의 대상이 되어야 한다 <br/>
따라서 개념적으로 **upstream**과 **downstream**은 **위치와 관점**에 따라 달라지며,  <br/>협업하는 개발자들이 정한 규칙에 따라 달라진다

<br />
<hr />

> ## `Git`에서 upstream 설정하는 방법 ✍️

<br />

1. 새로운 `remote` 이름 지정하기
```bash
$ git remote add upstream "내가 fork한 저장소의 원본 저장소 주소"
```

<br/>

2. `upstream`서버 내 새로운 변경 사항 있는지 확인 <br/><br/>
해당 명령어는 로컬 저장소 내 에 있는 브랜치와 upstream 저장소에 있는 브랜치 간의 차이점을 비교 <br/>

이를 통해 upstream 저장소에 있는 **새로운 브랜치 및 업데이트 된 브랜치**를 **로컬저장소로 가져올 수 있다**
   
```bash
$ git fetch upstream
```

<br />

3. 변경사항 가져오기
   
<br />
upstream에서 가져온 변경 사항을 *로컬저장소*로 가져오려면, <br />

가져올 로컬 브랜치를 체크아웃한후 => `merge`한다
<br />
예를 들어 병합하려는 upstream 브랜치가 `main`일 경우 다음과 같이 입력한다
<br />
```bash
$ git merge upstream/main
$ git merge upstream/"upstream 브랜치 이름"
```