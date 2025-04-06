# CVE-2022-22978: Spring Security Authorization Bypass
## 요약

- Spring Security 프레임워크는 Spring 기반 애플리케이션에서 인증 및 권한 부여 기능을 제공하는 보안 프레임워크이다.
- Spring Security 5.5.6, 5.6.3 및 그 이전 버전에서 `RegexRequestMatcher`를 사용하는 경우, URL 인코딩 취약점을 통해 권한 우회가 발생할 수 있다.
- 공격자는 `%2F`, `%0a` 등의 인코딩 문자열을 사용하여 관리자 페이지(`/admin`) 접근 권한을 우회할 수 있다.

## 환경 구성 및 실행

- `docker compose up -d` 을 실행하여 테스트 환경을 준비하였다.
- `http://localhost:8080/admin` 을 실행하여 관리자페이지에 대한 엑세스가 차단되어 있는지 확인한다.
- `http://localhost:8080/admin/%0atest` 을 실행하여 관리자 페이지에 접근한다.
