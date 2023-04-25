---
layout: post
title:  "유저 리스트 웹 페이지 구현하기 백엔드(Java, Spring)"
date:   2023-04-17 09:22:33 +0900
categories: Code Java Spring
published: true
---
```
자바 스프링 유저 리스트 기능 구현하기(백엔드)
- Controller, Service, Repository
- User-Mapper(xml)
```


# 사전준비
- 프론트에서 백엔드로 값 전달 로직 (ajax 등)
- Database 구축 (mysql 등)

DB에 있는 로그인 유저 리스트를 가져오는 방법에 대한 백엔드 관점에서의 설명입니다.
사전준비는 프론트에서 값 전달, DB구축되어 있어야 합니다.

- 추후에 프론트와, DB구축 부분도 추가 포스팅하겠습니다.

# 백엔드

Controller, Service(Implementation), Repository 그리고 Database에 매핑을 정의하여 구축해줍니다.

![Spring_Get_user_list1](/assets/img/Code/Java/Spring/2023-04-17-Spring_Get_user_list/Spring_Get_user_list1.jpg)

# 1. Controller

# 전체 코드

```java
...

@PostMapping("/user")
    public List<User> list(
        @RequestParam(value = "userid", required = false) String userid,
        @RequestParam(value = "username", required = false) String username
        ) throws Exception {
            User userlist = new User();
            userlist.setUserId(userid);
            userlist.setUserName(username);

            List<User> resultuserlist = new ArrayList<User>();
            resultuserlist = userService.selectUserList(userlist);
            return resultuserlist;
            }
```

## 1.1 PostMapping
```java
@PostMapping("/user")
```
- PostMapping으로 값을 받아왔습니다.
    - 해당 부분은 프론트에서 ajax를 통해 값을 전달받았습니다.

## 1.2 List<User>
```java
public List<User> list
```
- DB에서 User테이블의 정보를 리스트로 가져오기 위해 List로 선언했습니다.
    - User 클래스는 Model에 정의한 값입니다.

## 1.3 RequestParam
```java
@RequestParam(value = "userid", required = false) String userid,
@RequestParam(value = "username", required = false) String username
```
- "userid"에 대한 value를 프론트에 요청하여 가져옵니다.
- "required = false"는 해당 필드값이 존재하지 않아도 예외가 발생하지 않습니다.
    - username도 동일하게 작성되었습니다.

## 1.4 throws Exception
```java
throws Exception
```
- 의도적으로 예외를 발생시켜 로직을 만듭니다.
- throws는 자신을 호출한 메서드에게 책임을 전가하여 호출한 메서드에서 예외처리를 하도록 강요합니다. (예외를 상위클래스에 전달합니다)
    - 참고) throw는 강제로 예외를 발생시키는 것이고, 개발자의 판단에 따른 처리가 가능합니다.

## 1.5 new User()
```java
User userlist = new User();
userlist.setUserId(userid);
userlist.setUserName(username);
```
- userlist로 새로운 User클래스를 정의합니다.
- requestparam으로 가져온 값을 새로운 userlist 클래스로 정의해줍니다.
    - 프론트에서 입력한 값을 가져와 새로운 변수로 저장하기 위함입니다.
- Model에서 User클래스의 userid를 새롭게 정의하기 위한 함수입니다.
    - username도 동일하게 적용했습니다.

## 1.6 new ArrayList<User>()
```java
List<User> resultuserlist = new ArrayList<User>();
```
- resultuserlist로 새로운 User의 ArrayList를 정의해줍니다.
    - userlist를 리스트로 담기 위해 정의해줍니다.

## 1.7 userService.selectUserList(userlist)
```java
resultuserlist = userService.selectUserList(userlist);
```
- 위에서 정의한 userlist를 resultuserlist의 리스트로 정의합니다.
- userService는 사전에 정의한 값입니다.
    - selectUserList는 repository, service(implementation)에 사전에 정의한 값입니다.

## 1.8 return resultuserlist
```java
return resultuserlist;
```
- requestparam으로 프론트에서 입력한 값을 가져오고, 새롭게 리스트에 저장한 값을 return해줍니다.

# 2. Service

## 2.1 UserService
```java
public interface UserService {
    ...

    public List<User> selectUserList(User userlist);
}
```
- UserService 클래스를 정의하고, 새로운 userlist를 받아올 수 있게 정의해줍니다.

## 2.2 UserService implementation
```java
@Service
public class UserServiceImpl implements UserService {
    @Autowired
    private UserRepository repository;
    ...

    @Override
	public List<User> selectUserList(User userlist) {
        return repository.selectUserList(userlist);
	}
}
```
- UserService에 추가해주는 부분입니다.
- UserRepository를 repository로 정의하여 불러옵니다.
- repository에서 selectUserList에 userlist값으로 리스트 정의하고, 그 값을 return해줍니다.

# 3. Repository

```java
@Repository
public interface UserRepository {
    ...

	List<User> selectUserList(User userlist);
}
```
- repository에 selectUserList의 이름으로 리스트 정의하고 해당되는 값들은 User클래스의 userlist값들로 정의합니다.

# 4. User-Mapper.xml
```sql
<select id="selectUserList" resultMap="UserMap" parameterType="api.user">
    SELECT *
    FROM tableuser
    WHERE 1=1
    <if test="userid != null and userid != ''">
    and userid LIKE CONCAT('%',#{userid},'%')
    </if>
    <if test="username != null and username != ''">
    and username LIKE CONCAT('%',#{username},'%')
    </if>
</select>
```
## 각 부분에 대한 설명
```sql
SELECT *
```
- 모든 컬럼 선택합니다.

```sql
FROM tableuser
```
- "tableuser" 테이블에서 가져옵니다.

```sql
WHERE 1=1
```
- 1=1에서 가져옵니다. 항상 만족하며, WHERE를 쓰기 위한, 아래 조건을 성립시키기 위한 트릭입니다.

```sql
<if test="userid != null and userid != ''">
and userid LIKE CONCAT('%',#{userid},'%')
```
- if문은 userid가 null이거나 값이 없으면에 대한 조건문입니다.
- 조건문이 만족하면 아래 구문이 실행됩니다.
- WHERE에 이어서 and (둘다만족)
- userid컬럼에서 프론트에서 입력한 값이 저장된 변수 #{userid}값을 가져오는데, concat으로 userid 앞뒤에 '%'를 넣어 userid와 비슷한 값을 가져오기 위한 방법입니다.

```sql
<if test="username != null and username != ''">
and username LIKE CONCAT('%',#{username},'%')
```
- username도 동일하게 작성되었습니다.
- userid와 username도 값이 입력되면, 둘다 만족하는 값을 가져오기 위해 and로 이어집니다.

긴 글 읽어주셔서 감사합니다 :)

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D