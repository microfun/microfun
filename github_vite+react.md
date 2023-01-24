# 깃허브 페이지 ( vite + react )

#### 깃허브 페이지 연결 및 푸시

```
…or create a new repository on the command line
echo "# microfun" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/microfun/microfun.git
git push -u origin main
```

```
…or push an existing repository from the command line
git remote add origin https://github.com/microfun/microfun.git
git branch -M main
git push -u origin main
```

## Deploy Vite + Github Pages

##### 2022-12-30

1. npm create vite@latest
2. npm install
3. npm run dev
4. npm i gh-pages -D

vite.config.js 파일 위치에서
base: "/microfun", // 추가 깃허브 페이지 ===> 아래 내용 추가됨.

base 부분을 없애니깐 https 정상 동작함.

```java
// https://vitejs.dev/config/
export default defineConfig({
	plugins: [react()],
	base: "/microfun/",
});
```

5. npm run build
6. package.json 파일 내에
   script "deploy":"gh-pages -d dist" 내용 추가

```java
"scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "deploy": "gh-pages -d dist"
},
```

7. npm run deploy

git add .
git commit -m "deploy"
git push

### server responded with a status of 404 () 에러 발생

- 위와 같이 작업을 하면 깃허브 페이지를 연결하는것은 문제가 없었다.
- 그러나 도메인을 연결하고 https 를 사용하려다 보니깐~~ 위와 같이 404 에러가 발생

- vite.config.js 에서
  base: "/microfun/" 을 입력 하면.
  https://microfun.github.io/microfun/index.html <-- 주소 입력시 접속이 가능함.

- 테스트 끝에.. base 부분 /microfun/ 이부분을 제거 하니깐 정상 동작이 되었습니다.

```java
// https://vitejs.dev/config/
export default defineConfig({
	plugins: [react()],
});
```

홈페이지 수정후 deploy를 하면
gh-pages -d dist가 실행 되면서 깃허브 페이지가 수정됩니다.

# 깃허브 페이지 ( vite + react )

#### 깃허브 페이지 연결 및 푸시

```
…or create a new repository on the command line
echo "# microfun" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/microfun/microfun.git
git push -u origin main
```

```
…or push an existing repository from the command line
git remote add origin https://github.com/microfun/microfun.git
git branch -M main
git push -u origin main
```

## Deploy Vite + Github Pages

##### 2022-12-30

1. npm create vite@latest
2. npm install
3. npm run dev
4. npm i gh-pages -D

vite.config.js 파일 위치에서
base: "/microfun", // 추가 깃허브 페이지 ===> 아래 내용 추가됨.

base 부분을 없애니깐 https 정상 동작함.

```java
// https://vitejs.dev/config/
export default defineConfig({
	plugins: [react()],
	base: "/microfun/",
});
```

5. npm run build
6. package.json 파일 내에
   script "deploy":"gh-pages -d dist" 내용 추가

```java
"scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "deploy": "gh-pages -d dist"
},
```

7. npm run deploy

git add .
git commit -m "deploy"
git push

### server responded with a status of 404 () 에러 발생

- 위와 같이 작업을 하면 깃허브 페이지를 연결하는것은 문제가 없었다.
- 그러나 도메인을 연결하고 https 를 사용하려다 보니깐~~ 위와 같이 404 에러가 발생

- vite.config.js 에서
  base: "/microfun/" 을 입력 하면.
  https://microfun.github.io/microfun/index.html <-- 주소 입력시 접속이 가능함.

- 테스트 끝에.. base 부분 /microfun/ 이부분을 제거 하니깐 정상 동작이 되었습니다.

```java
// https://vitejs.dev/config/
export default defineConfig({
	plugins: [react()],
});
```

홈페이지 수정후 deploy를 하면
gh-pages -d dist가 실행 되면서 깃허브 페이지가 수정됩니다.
