---
project: gameland
stars: 1
description: 모노레포 package centric 방식의 JS 게임 모음 저장소
url: https://github.com/HyunYuJin/gameland
---

gameland
========

Configuring Apps
----------------

```
$ pnpm create vite 프로젝트명 --template react-ts
```

Settings package.json
---------------------

공유 프로젝트에 대한 참조를 추가하고 프로젝트 이름을 업데이트해야 합니다.

// package.json
{
	"name": "@gameland/프로젝트명",
	// ...
	"dependencies": {
		"@gameland/shared": "workspace:\*",
		// ...
  }
}

설치
--

pnpm-workspace.yaml 파일에 등록된 모든 App들은 추적되고 있으므로 다음 명령어로 모든 App의 패키지를 한방에 설치할 수 있다.

```
$ pnpm install
```

* * *

게임 소개
-----

### MBIT

시작 페이지

질문 페이지

결과 페이지

당신의 개발자 유형은 뭘까요?

-   백엔드 개발
-   프론트엔드 개발
-   데이터분석과 인공지능
-   정보보안
-   게임 개발
