# lecture-jwt-tutorial
- 인프런 JWT 강의 학습용 repo

## 강의 정보
- 강의 주소 : https://www.inflearn.com/course/%EC%8A%A4%ED%94%84%EB%A7%81%EB%B6%80%ED%8A%B8-jwt/dashboard
- 소스 코드 : https://github.com/SilverNine/spring-boot-jwt-tutorial

# 강의별

## 1강

## 2강
- Security 설정이 예전 버전이다. 5.7.0-M2 버전 부터 `WebSecurityConfigurerAdapter`이 deprecated 되었다.
  - 이에 따라 이제는 상속을 받지 않고, 그냥 일반적인 @Configuration 클래스에서 HttpSecurity를 매개변수로 받는 Bean을 등록한다. 
  - 참고 링크 :  <https://spring.io/blog/2022/02/21/spring-security-without-the-websecurityconfigureradapter>
- h2의 빌트인 테이블로 USER가 추가됨에 따라 변경이 필요하다.
  - 테이블 명을 users로 변경할 수 있다.
  - 혹은 h2 버전을 강제로 낮추면 된다고 한다.
  - 참고 링크 : <https://www.inflearn.com/questions/546219>

## 4강
- password 저장 부분에 Security 버전에 따른 변경 사항이 있다.
  - 패스워드의 prefix로 저장된 비밀번호의 알고리즘 id가 필요하다 e.g. 원래비밀번호 -> {bycrypr}원래비밀번호
  - 사용자가 요청한 패스워드를 인코드 후 저장 값과 비교할 텐데, 이 인코더를 등록해야 한다.
  - bcrypt의 경우 아래와 같이 빈을 추가해준다.
  ```java
    @Bean
    public static PasswordEncoder passwordEncoder() {
        return PasswordEncoderFactories.createDelegatingPasswordEncoder();
    }
  ```
  

# 완강 이후 추가 사항
- [ ] 강의 소스 부분의 테스트 코드를 추가하기