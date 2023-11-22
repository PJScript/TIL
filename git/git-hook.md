# 목차

1. [git hook 이란](#GIT HOOK)
2. [추가](#추가)

## GIT HOOK

git hook 이란 리포지토리에서 특정 이벤트가 발생할 때마다 자동으로 실행되는 스크립트이다. github와 혼동 금지 github 는 git 시스템을 활용한 "서비스" 이고 여기서 말하는건 "git" 이다.

commit, push 직전 혹은 직후에 작동할 스크립트를 지정해두는 과정이라고 생각 하면 된다.
주로 husky 라는 라이브러리를 사용하여 설정한다.

```
// 우선 husky를 설치한다.
npm i husky --save-dev

// 이후 아래 명령어 입력하면 .husky 라는 폴더가 생성된다.
npx husky install

// 아래 명령어를 입력하여 commit 전, push 전 상황에 무슨 스크립트를 실행 할건지 지정할 수 있다.
// "npm run format", "npm run lint" 부분이 스크립트 실행에 해당하는 부분이다.
// 아래 예제는 package.json에 작성해두고 실행하는 방식이다.
npx husky add .husky/pre-commit "npm run lint"
npx husky add .husky/pre-push "npm run lint"
```

위 작업이 완료되었다면 commit 전에 lint를 체크하고 push 전에도 lint를 체크한다.
위 예제는 commit, push 둘다 lint만 체크하고 있는데, commit 상황에서 이미 lint 체크를 했으니 push 상황에서는 브랜치 체크를 하면 좋을 듯 하다.

main 브랜치 혹은 master 브랜치에 직접 push를 방지하는 그런 스크립트가 있으면 좋을 듯 하다.

## 추가

...
