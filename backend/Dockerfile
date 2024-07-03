# 베이스 이미지 선택
FROM python:3.12-slim

# 작업 디렉토리 설정
WORKDIR /app

# GitHub에서 소스 코드 복사
RUN apt-get update && apt-get install -y git
RUN git clone https://github.com/haea9412/rive.git --branch be_ha .

RUN pip install --no-cache-dir -r requirements.txt

RUN python --version

WORKDIR /app/myapi

# 포트 설정
EXPOSE 8000

# 서버 실행 명령어
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
