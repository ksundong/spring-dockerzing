# spring-dockerzing

[Spring 공식 가이드](https://spring.io/guides/gs/spring-boot-docker/) 를 따라가면서 spring boot dockerizing을 실습한다.

예제를 따라하다가 오류가나서 공식 문서에 contribute를 했다.

https://github.com/spring-guides/gs-spring-boot-docker/pull/89

## dependency와 application 분리

```
mkdir -p build/dependency && (cd build/dependency; jar -xf ../libs/*.jar)
```

이걸로 압축 해제한다.

Entrypoint에 class를 직접 적어주는 것은 간접 참조보다 훨씬 빨리 실행이 가능하기 때문에 사용.

BOOT-INF에 관련된 정보들이 다 들어있다.

## OCI Image 빌드하기

spring boot는 OCI Image를 빌드하는 방법을 제공한다. OCI는 컨테이너 기술의 표준과 같은 개념인듯.

```
./gradlew bootBuildImage --imageName=springio/gs-spring-boot-docker
```
