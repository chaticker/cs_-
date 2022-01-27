## VO와 DTO, BO, DAO란?

1. DAO(Data Access Object): DB에 접근하여 실제 데이터를 조회 또는 조작하는 클래스, Repository 또는 Mapper에 해당함

2. BO(Business Object): 여러 DAO를 활용해 비지니스 로직을 처리하는 클래스, Service에 해당함

3. DTO(Data Transfer Object): 데이터를 주고 받기 위해 사용하는 클래스

4. VO(Value Object): 실제 데이터만을 저장하는 클래스

---

## WAS와 WS의 차이에 대해 설명해주세요.

- WAS(Web Application Server): 비지니스 로직을 넣을 수 있음

        Tomcat, PHP, ASP, .Net 등

- WS(Web Server): 비지니스 로직을 넣을 수 없음

        Nginx, Apache 등

---

## Servlet, JSP의 차이점을 설명해주세요.

- Servlet - Container가 이해할 수 있게 구성된 순수 자바 코드로만 이루어진 것(Html in JAVA)

- JSP(Java Server Page) - html기반에 JAVA코드를 블록화하여 삽입한 것(JAVA in Html)
