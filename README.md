# lecture-jwt-tutorial
- 인프런 JWT 강의 학습용 repo

# 강의별

## 1강

## 2강
- Security 설정이 예전 버전이다. 5.7.0-M2 버전 부터 `WebSecurityConfigurerAdapter`이 deprecated 되었다.
  - 이에 따라 이제는 상속을 받지 않고, 그냥 일반적인 @Configuration 클래스에서 HttpSecurity를 매개변수로 받는 Bean을 등록한다. 
  - 참고 링크 :  <https://spring.io/blog/2022/02/21/spring-security-without-the-websecurityconfigureradapter>

# 완강 이후 추가 사항
- [ ] 강의 소스 부분의 테스트 코드를 추가하기