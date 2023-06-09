+++
title = "Docker : 가상화 플랫폼을 넘어서"
date = "2023-05-28T21:29:20+02:00"
tags = ["Docker"]
categories = ["programming"]
description = "Docker"
banner = "img/banners/docker1.jpeg"
authors = ["김원형"]
+++

---
# Docker 가상화 플랫폼

소프트웨어 개발과 배포를 Docker는 개발자들에게 많은 혜택을 제공하고 있습니다. 컨테이너 기반 가상화 기술을 통해 Docker는 애플리케이션을 격리된 환경에서 실행하고 관리하는 간편한 방법을 제공합니다.

## 가상화 종류

- 개발환경 가상화
  - 개발 인터프리터
  - 라이브러리
- OS 수준 가상화:리눅스 컨테이너
  - OS의 독립된 공간 격리
  - isolation
- 머신가상화
  - 하이퍼바이저

### Docker 이미지

Docker의 가장 중요한 개념 중 하나는 "이미지"입니다. 
이미지는 애플리케이션을 실행 가능한 패키지로, 개발자는 애플리케이션을 이미지로 빌드하여 필요한 환경 설정을 할 수 있습니다.

이미지를 사용하여 Docker는 "컨테이너"라는 실행 환경을 생성합니다. 
컨테이너는 이미지의 인스턴스로, 격리된 환경에서 애플리케이션을 실행합니다. 또한, 호스트 시스템과 독립적으로 실행되므로 다양한 환경에서 일관되게 실행할 수 있어 더욱 효율적으로 만들어 줍니다.
---
