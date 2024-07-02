FROM node:14-alpine

# 앱 디렉토리 생성
WORKDIR /app

# package.json 및 package-lock.json 복사하여 종속성 설치
COPY package*.json ./
RUN npm install

# 앱 소스 코드 복사
COPY . .

# 앱 빌드
RUN npm run build

# NGINX 설치 및 설정
FROM nginx:alpine
COPY --from=0 /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
