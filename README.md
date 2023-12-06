## 깃허브
    - https 지원
        SSL 인증서 있어야 PHP서버 & MYSQL서버에 접근 가능
        SSL 인증서 있어야 JSP서버 & MYSQL서버에 접근 가능
        
    1. 깃허브에 저장소(리파지토리) 생성
        - 깃허브 로그인 후 왼쪽에 저장소 이름 적고 NEW
        - Create a new repository 페이지로 이동
        - 하단 버튼 creating repository 클릭
        ```
            Repository name : kurly
            origin : https://github.com/SIEUN-813/git_test1.git
        ```
    
    2. settings > pages > Build and deployment 아래에 Source 를 Deploy from a branch 선택 > Branch 를 master 선택하면 배포주소.io 나옴

    3. package.json 파일 안에 배포주소 넣기
        (예시)"homepage": "https://myusername.github.io/my-app" 
            => "homepage": "https://SIEUN-813.github.io/kurly"

    4. 깃설정
        * git init
        * ls -la

    5. 깃환경설정    
        - 사용자이름('SIEUN-813') & 사용자이메일('pse0813@naver.com') 등록
            * git config user.name 'SIEUN-813' 
            * git config user.email 'pse0813@naver.com' 
        - 등록 확인
            * git config user.name
            * git config user.email
            
    6. 리모트 오리진 추가|삭제
        * git remote add origin https://github.com/SIEUN-813/kurly.git
        - origin 확인
            * git remote -v 

    ( 파일 수정시 여기서부터 다시 실행)
    7. add 스테이징
        - 모든파일전송
            * git add *
        - 선택한파일전송
            * git add 파일이름

    8. commit 커밋
        - git commit -m '전송메시지'
            * git commit -m 'kurly 프로젝트 배포'

    9. push 푸쉬
        * git push origin master

    10. Deployment
        - https://create-react-app.dev/docs/deployment/ 로 들어가서 GitHub Pages
            10-1. Add homepage to package.json
                package.json 파일 안에 "homepage": "https://myusername.github.io/my-app" 넣기

            10-2. Install gh-pages and add deploy to scripts in package.json
                10-2-1. * npm i gh-pages
                10-2-2. package.json 파일 안에 "scripts"에 넣기 

                            (master 배포시)
                            "predeploy": "npm run build",   
                            "deploy": "gh-pages -b master -d build"

                            (branch 배포시)
                            "predeploy": "npm run build",                 
                            "deploy": "gh-pages -d build"

            10-3. Deploy the site by running npm run deploy
                * npm run deploy

            10-4. 완료시 터미널에 Published 찍힘
