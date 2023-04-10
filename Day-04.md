# 1:M 관계

<br>

한쪽이 관계를 맺은 쪽의 여러 객체를 갖는 것을 의미이다.  
부모에 자식이 종속된 관계이다.  
관계에 맞춰서 데이터가 삽입, 삭제되며 관계가 없는 데이터를 가비지 데이터라고 한다.

<br>

![스크린샷 2023-04-10 오후 4 02 11](https://user-images.githubusercontent.com/81137234/230846225-38b34678-d158-44fd-9d72-837ea5af3a90.png)

<br>

위의 구조를 가지며, 위 같은 것을 Directory에서 흔히 볼 수 있다.  

<br>

![스크린샷 2023-04-10 오후 4 03 54](https://user-images.githubusercontent.com/81137234/230846514-2a55895e-1614-4ce5-a588-693749542d34.png)

<br>

```
select * from 학년
insert into 학년 values(1, '1학년')
insert into 학년 values(1, '3학년')
insert into 학년 values(1, '2학년')

select * from 반
insert into 반 values(1, 1, '1반')
insert into 반 values(2, 1, '1반')
insert into 반 values(3, 1, '1반')


```

데이터를 우선 넣는다.

<br>

```
select a.학년번호, a.학년이름, b.반이름 from 학년 a
join 반 b on a.학년번호 = b.학년번호
```

외래키로 지정되어 있지 않으므로 Join을 해서 1:m 관계를 조회할 수 있다.  
참고로 a.학년번호 처럼 primary key는 필수적으로 DBA에게 전달해주는 것이 좋다.

<br>

