+++
title = "Hugo 개발 절차"
date = "2023-05-24T21:29:20+02:00"
tags = ["HUGO"]
categories = ["programming"]
description = "정적 웹사이트 Hugo를 활용한 개발 방법"
banner = "img/banners/hugo-banner-2.jpeg"
authors = ["성경식"]
+++
# Hugo, 개발 절차
1. Hugo 설치
```Bash
apt install hugo
``` 
2. 프로젝트 생성
```bash
hugo new site <site-name>
```
3. 테마 사용
```bash
git clone <theme-url>
```
4. 파일 만들기
```bash
hugo new <page-name>
```
5. 테스트
```bash
hugo server --bind=0.0.0.0
```
6. 빌드
```bash
hugo -t <테마이름>:hugo-developer-portfolio
```
7. 퍼블리싱
```bash
cd <public 경로>
git add .
git commit -m "<commit-message>"
git push
```   


