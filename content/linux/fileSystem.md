---
title: "File System"
date: 2023-05-23T10:53:57Z
banner: "img/banners/linux/banner-7.jpg"
categories: ["programming"]
tags: ["linux"]
draft: true
---

# Linux 파일 시스템

![img](../../img/content/linux/file.png)

## 리눅스 파일 시스템 구조
***
리눅스 시스템의 디렉토리는 전체적으로 역 트리 구조로 이루어져 있다
## /
***
최상위 디렉토리인 루트 디렉토리를 의미한다. 루트 디렉토리는 리눅스의 모든 디렉토리들의 시작점이다. 모든 디렉토리를 절대경로로 표기할 때에 이 디렉토리로부터 시작해야 한다.   

## /bin
***
mv, ls, rm과 같은 기본적인 명령어가 저장되어 있는 디렉토리이다.

## /boot
***
리눅스 부트로더(Boot Loader)가 존재하는 디렉토리이다.

## /dev
***
시스템 디바이스 파일이 저장되어있는 디렉토리이다. 하드 디스크나 ROM에 관한 장치파일이 존재한다.

## /etc
***
시스템의 거의 모든 설정 파일이 존재하는 디렉토리이다. sysconfig 파일과 passwd 파일 등이 저장되어있다.

## /home
***
모든 사용자들의 홈 디렉토리가 존재하는 디렉토리이다. 새로운 사용자를 생성하면 이 디렉토리에는 대부분 사용자 ID와 동일한 이름의 디렉토리가 생성된다.

## /lib
***
공유 라이브러리와 커널 모듈들이 존재하는 디렉토리이다.

## /mnt
***
마운트 포인트 디렉토리이다. 하지만 꼭 마운트를 이 디렉토리에만 해야 하는 것은 아니다.

## /proc
***
일종의 가상 파일 시스템으로 메모리 정보만을 담고 있다. 현재 메모리에 존재하는 실행 중인 작업에 관한 파일이 저장되어 있다. ```ps``` 명령어가 이 디렉토리에서 프로세스 정보 등을 참조한다.

## /root
***
시스템의 최고관리자인 root의 홈 디렉토리이다.

## /sbin
***
root만 사용할 수 있는 명령어들이 존재한다.

## /tmp
***
임시 파일이 존재하는 디렉토리이다.

## /usr
***
일반 사용자들이 주로 사용하는 디렉토리이다.

## /var
***
시스템 작동 중에 변경되는 데이터를 일시적으로 저장하기 위한 디렉토리이다.