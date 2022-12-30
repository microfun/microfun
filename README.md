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
base: "/microfun", // 추가 깃허브 페이지

```java
export default defineConfig({
	plugins: [react()],
	base: "https://www.pmong.co.kr/",
});
```

base /microfun/
이것에서 도메인 연결을 했기 때문에..
base: "https://www.pmong.co.kr/",
이렇게 변경 시켜줌..

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
