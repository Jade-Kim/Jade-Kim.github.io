---
title: "Step by Step: python virtual environment and install django project"
excerpt: "파이썬 가상 환경을 설치하고 가상 환경에서 Django 와 django 프로젝트를 설치하는 절차를 소개한다."
header:
  overlay_color: "#4B8BBE"
  overlay_filter: rgba(0, 0, 0, 0.5)
categories:
  - Python
tags:
  - 웹개발
---

Django를 Global 또는 가상 환경에 설치할 때 Python은 특정 애플리케이션에 필요한 isolated environment 를 사용할 것을 권장한다.

이를 위해 가상환경에서 Django 와 프로젝트를 작업할 필요가 있다. Python의 표준 라이브러리에는 가상환경을 만들어주는 venv 모듈이 포함되어 있어 venv 모듈을 사용하는 것이 일반적이다.

또한 venv 모듈은 시스템 경로에 django-admin 이라는 커맨드라인 유틸리티를 설치하여 개발자에게 편리함을 준다. django-admin 다양한 관리 작업을 수행하도록 해주는 유틸리티이다. 예를 들어, 프로젝트 및 앱 만들기, 데이터 모델과 구조가 일치하는 데이터베이스 테이블 생성을 위한 마이그레이션 수행, 개발 서버 실행 등의 작업을 수행할 수 있다.

파이썬 가상 환경을 설치하고 django 설치 및 프로젝트 시작을 위해서 터미널을 열고 아래 커맨드를 차례로 실행한다.

```python
# 1. 파이썬 폴더(디렉토리) 만들기
mkdir 폴더이름
cd 폴더이름

# 2. 파이썬 가상 환경 만들기
python3 -m venv 가상환경이름

# 3. 파이썬 가상 환경 활성화 시키기
# 윈도우
.\가상환경이름\Scripts\activate
#맥
source 가상환경이름/bin/activate

# 위 명령어를 실행하여 가상환경을 활성화시키면 커맨드 프롬프트에 괄호로 (가상환경이름) 이 표시되는 것을 확인할 수 있다!!!

# 4. Django 설치하기
pip3 install django

# 5. Django 설치 유무 및 버전 확인하기
ptyhon3 -m django version

# 6. 파이썬 프로젝트 만들기
django-admin startproject 프로젝트이름

# 7. 프로젝트 디렉토리로 이동하기
cd 프로젝트이름

# 8. 파이썬 프로젝트내에 App 만들기
python3 manage.py startapp 앱이름

# 9. 프로젝트 서버 시작하기
python3 manage.py runserver

# 10. localhost URL 복사하여 브라우저에서 확인하기
Starting development server at http://127.0.0.1:8000/

# 서버 중단하기: Ctrl + C

# 파이썬 가상 환경 비활성화 시키기
deactivate

```
