# base 이미지 노드 이미지!! 16버전, alpine 작은 단위의 리눅스 어떤 베이스 이미지 쓸거냐
FROM node:16-alpine

# 컨테이너 안에 어떤 경로로 사용할 건가?
# /app이라는 폴더 안에 우리 프로젝트와 관련된 파일을 복사해온다.
# 어떤 디렉토리에 우리 어플리케이션을 복사해 올것인가
WORKDIR /app

# 현재 경로인 app으로 자주 수정되지 않는 파일을 먼저 복사해옴
COPY package.json package-lock.json ./

# npm install로 package.json 내의 라이브러리 설치!! -> install은 뭐랄까 최신판을 설치 할 수도 있다
# npm ci? package-lock.json의 우리가 개발할 때 썼던 파일들이 정확하게 설치된다!!
RUN npm ci


COPY index.js .

# 노드 실행할 거고 index.js 실행해!!
ENTRYPOINT [ "node", "index.js" ]
