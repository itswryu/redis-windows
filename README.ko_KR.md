### [English](https://github.com/itswryu/redis-windows/blob/main/README.md) | [한국어](https://github.com/itswryu/redis-windows/blob/main/README.ko_KR.md) | [简体中文](https://github.com/itswryu/redis-windows/blob/main/README.zh_CN.md)

# Redis Windows 버전

### GitHub Actions를 활용한 최신 Windows용 Redis 빌드

Redis의 Windows 버전은 GitHub Actions의 자동화된 빌드 기능을 활용하여 실시간으로 최신 버전을 Windows 시스템에 맞게 컴파일합니다.


### 세 가지 실행 모드 제공

start.bat 스크립트를 실행**하여 한 번의 클릭으로 시작

명령줄 명령어 사용

시스템 서비스로 실행


## 명령줄을 통한 실행
cmd에서 실행
```shell
redis-server.exe redis.conf
```
powershell에서 실행
```shell
./redis-server.exe redis.conf
```

## 서비스 생성
Redis를 시스템 서비스로 설치하여 부팅 시 자동으로 시작되도록 설정할 수 있습니다.
아래 명령어를 관리자 권한으로 실행하세요. 경로의 `RedisService.exe`는 실제 저장 경로로 변경해야 합니다.

```shell
sc.exe create Redis binpath=C:\Software\Redis\RedisService.exe start= auto
```
서비스 시작
```shell
net start Redis
```
서비스 중지
```shell
net stop Redis
```
서비스 제거
```shell
sc.exe delete Redis
```

![image](https://user-images.githubusercontent.com/515784/215540157-65f55297-cde2-49b3-8ab3-14dca7e11ee0.png)


프로젝트 홈: https://github.com/itswryu/redis-windows

### 감사의 말
[![NetEngine](https://avatars.githubusercontent.com/u/36178221?s=180&v=4)](https://www.zhihu.com/question/424272611/answer/2611312760)
[![JetBrains Logo (Main) logo](https://resources.jetbrains.com/storage/products/company/brand/logos/jb_beam.svg)](https://www.jetbrains.com/?from=redis-windows)

### 면책 조항
이 프로젝트는 학습 및 로컬 개발 목적으로 사용을 권장합니다. 프로덕션 환경에서는 Redis 공식 가이드를 따라 Linux에서 배포하는 것을 권장합니다. 본 프로젝트로 인해 발생하는 어떠한 손실에 대해서도 책임지지 않으며, 오직 학습과 교류를 위해 제공됩니다.