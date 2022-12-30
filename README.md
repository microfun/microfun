"# microfun"

'''
…or create a new repository on the command line
echo "# microfun" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/microfun/microfun.git
git push -u origin main
'''

'''
…or push an existing repository from the command line
git remote add origin https://github.com/microfun/microfun.git
git branch -M main
git push -u origin main
'''

# Deploy Vite + Github Pages

### 2022-12-30

1. npm create vite@latest
2. npm install
3. npm run dev
4. npm i gh-pages -D

vite.config.js 파일 위치에서
base: "/microfun", // 추가 깃허브 페이지

5. npm run build
6. package.json 파일 내에
   script "deploy":"gh-pages -d dist" 내용 추가

7. npm run deploy
8.
