---
title: "Linux command"
date: "2023-05-23T10:25:30Z"
tags: ["linux", "command"]
categories: ["programming"]
banner: "img/banners/linux/banner-6.jpg"
draft: true
---

# Linux 기본 명령어
***
* [1. pwd](#pwd)   
* [2. mkdir](#mkdir)   
[mkdir options](#options)
* [3. ls](#ls)   
[ls options](#options-1)
* [4. cd](#cd)   
* [5. rm](#rm)   
[rm options](#options-2)   
* [6. cp](#cp)  
* [7. mv](#mv)
***

## pwd
***
pwd는 prind working directory의 약자로 현재 디렉토리의 경로를 보여주는 명령어이다. 현재 디렉토리가 /home/ubuntu라면 pwd를 입력하면 터미널 화면에 /home/ubuntu가 출력된다.

## mkdir
***
mkdir은 make directory의 약자로 새로운 디렉토리를 생성할 때 사용한다. 아래의 DIRECTORY의 위치에 생성하고자 하는 디렉토리를 입력한다. 공백을 두고 여러 개의 디렉토리를 입력으로 넣으면 디렉토리들을 여러 개 만들 수 있다.
```
mkdir [OPTION]... DIRECTORY...
```
e.g) mkdir&nbsp;&nbsp;./test1&nbsp;&nbsp;test2&nbsp;&nbsp;../test3/test4&nbsp;&nbsp;/home/test5   
이 명령어는 현재 디렉토리에 test1, test2 디렉토리를, 이전 디렉토리에 있는 test3 디렉토리에 test4를, 홈디렉토리에 test5를 생성하라는 뜻이다. 옵션이 없을 때 이전 디렉토리에 test3가 존재하지 않을 경우, 오류가 발생한다.
### options
> -p: 상위 디렉토리도 함께 생성한다.   
> -m: 디렉토리를 생성할 때 해당 디렉토리에 대한 권한을 설정한다.   
> -v: 디렉토리를 생성할 때 생성할 디렉토리에 대한 메시지를 출력한다.

위의 예시에서 -p를 포함하면, 즉 아래의 명령어를 입력하면 test3 디렉토리가 존재하지 않는 경우에 test4를 test3의 하위 디렉토리로 하여 test3와 함께 test4를 생성한다.   
```
mkdir -p ./test1 test2 ../test3/test4
```

## ls
***
ls는 list의 약자로 디렉토리 내에 있는 모든 파일과 디렉토리의 목록을 출력한다. 옵션이 없으면 숨김 파일은 출력하지 않는다.
```
ls [OPTION]... [FILE]...
```
[FILE]에는 default로 현재 디렉토리로 설정되어 있고 특정 디렉토리의 경로를 입력으로 넣으면 그 디렉토리에 있는 모든 파일과 디렉토리의 목록을 출력한다. 또한 mkdir과 같이 공백을 두고 여러 입력을 넣을 수 있다.   
e.g) ls   
현재 디렉토리에 있는 모든 파일과 디렉토리의 목록을 출력한다.   
e.g) ls&nbsp;&nbsp;../   
이전 디렉토리에 있는 모든 파일과 디렉토리의 목록을 출력한다.   
e.g) ls&nbsp;&nbsp;/home/ubuntu&nbsp;&nbsp;../   
/home/ubuntu와 이전 디렉토리에 있는 모든 파일과 디렉토리의 목록을 출력한다.   
### options
> -a: 숨겨진 파일과 디렉토리도 함께 출력한다.   
> -l: 파일 종류, 각 파일의 권한, 링크 수, 소유자, 그룹, 크기(바이트), 최종 수정 시간을 표시한다.   
> -S: 파일 크기 순으로 정렬해서 출력한다.   
파일의 종류에는 파일, 디렉토리, 링크, 파이프가 있고 각각 -, d, l, p로 구분된다.
e.g) ls -l  

```drwxr----x 1 root 4096 May 23 22:25 example```   
```ls -l```를 실행하여 보이는 목록 중 example 디렉토리에 대한 정보이다. ```drwxr----x```에서 d는 example이 디렉토리임을 나타내고 나머지 9자리는 이 디렉토리에 대한 권한 정보를 표시한 것이다. 권한에 대한 정보는 세자리씩 세 부분으로 나뉘어져 있는데 각각 소유자, 그룹, 사용자에 대한 권한을 나타낸다. 이 출력에서 알 수 있는 것은 이 디렉토리의 소유자는 root이고 root rwx(읽기, 쓰기, 실행)이 모두 허용된 것이고, 그룹은 r(읽기), 사용자는 x(실행)만이 허용되었다는 의미이다.   
나머지 정보는 example 디렉토리에 있는 링크의 수는 1, 이 디렉토리의 소유자는 root, 크기는 4096이며 최종 수정 시간은 5월 23일 22시 25분임을 뜻한다.

```-rwx---w---x 1 ubuntu 1024 May 22 09:00 example.txt```   
```ls -l```를 실행하여 출력된 결과가 위와 같다면 example.txt는 파일이고 나머지 부분은 차례대로 권한, 링크의 수, 소유자, 파일의 크기, 최종 수정 일자를 의미한다.   

e.g) ls -a   
현재 디렉토리에 있는 모든 파일과 디렉토리를 숨겨진 파일과 디렉토리까지 보여준다. 숨겨진 파일과 디렉토리는 .(점)으로 시작하는 파일 또는 디렉토리이다. 대표적으로 ```git init``` 후에 생성되는 .git 디렉토리가 숨겨진 디렉토리이다.   
e.g) ls -al   
옵션 l과 a를 함께 사용한 것이다. ```ls -al```는 ```ls -a -l```과 같고 이는 ```ll```으로 줄여서 사용할 수 있다. 이는 리눅스에 기본적으로 등록되는 alias이다. ```alias```는 긴 명령어를 별칭으로 대체하여 사용하게 하는 기능이다.   

## cd
***
cd는 change directory의 약자로 실행시 다른 디렉토리로 이동한다.   
```
cd [OPTION] [dir]
```

e.g) cd&nbsp;&nbsp;..   
이전 디렉토리로 이동한다.
e.g) cd&nbsp;&nbsp;~   
"~"는 홈디렉토리를 의미한다. 따라서 홈디렉토리로 이동한다.   
e.g) cd -   
현재 디렉토리로 이동하기 전 가장 마지막으로 위치해 있던 디렉토리로 이동한다.   

## rm
***
rm은 remove의 약자로 파일 또는 디렉토리를 삭제하는 명령어이다.   
```
rm [OPTION]... [FILE]...
```
```rm```도 ```mkdir```과 마찬가지로 [FILE]에 여러 입력을 넣으면 여러 개의 파일 또는 디렉토리를 삭제할 수 있다. 다만, 특정 옵션이 없으면 디렉토리를 삭제할 수 없다.   

### options
> -f: 파일 또는 디렉토리를 강제로 삭제한다.  
> -r: 하위 디렉토리를 포함해 모든 대상을 삭제한다.   

e.g) rm -rf ./test   
test가 비어있든 비어있지 않든 현재 디렉토리에 존재하는 test 디렉토리를 강제로 삭제한다. test가 파일이라면 현재 디렉토리에 있는 test 파일을 삭제한다.   

## cp
***
copy의 약자로 어떤 파일이나 디렉토리를 특정 디렉토리로 복사할 때 사용한다.
```
cp [OPTION]... SOURCE... DIRECTORY
```
SOURCE에 복사할 파일 또는 디렉토리를 여러 개를 입력으로 넣으면 DIRECTORY에 입력으로 넣은 디렉토리로 여러개가 복사된다.   
e.g) cp&nbsp;&nbsp;../test/test.txt&nbsp;&nbsp;../example/&nbsp;&nbsp;.   
이전 디렉토리에 있는 test 디렉토리에 존재하는 test.txt와 이전 디렉토리에 존재하는 example 디렉토리를 현재 디렉토리에 복사한다.   

## mv
***
move의 약자로 파일 또는 디렉토리를 특정 디렉토리로 이동시킬 때 사용한다.   
```
mv [OPTION]... SOURCE... DIRECTORY
```
SOURCE에 입력으로 넣은 파일 또는 디렉토리를 DIRECTORY에 입력으로 넣은 디렉토리로 이동시킨다. SOURCE에 공백을 두고 여러 입력을 넣을 수 있다. 한편 이 명령어를 이용해 파일 또는 디렉토리의 이름을 변경할 수 있다. 이름을 변경할 때에는 SOURCE에 입력을 여러 개를 넣으면 오류가 발생한다.   
e.g) mv&nbsp;&nbsp;test&nbsp;&nbsp;./test1   
test를 test1으로 이름을 변경한다.   
e.g) mv&nbsp;&nbsp;test&nbsp;&nbsp;/home/ubuntu/test2&nbsp;&nbsp;../   
현재 디렉토리에 있는 test와 /home/ubuntu에 존재하는 test2를 이전 디렉토리로 옮긴다.   