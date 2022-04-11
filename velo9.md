프로젝트를 제대로 소개
- 1) 프로젝트 제목/주제
- 2) Demo 링크
- 3) 제작 기간 & 참여 인원
- 4) 사용한 기술( 기술 스택)
- 5) (필요한 경우) ERD
- 6) 핵심 기능(코드로 보여주거나 코드 링크)
- 7) 트러블슈팅(문제해결) 경험 / 자랑하고 싶은 코드
- 8) 회고 / 느낀점(필수는 아니지만 포함하는 것이 좋음) -> 비하인드 스토리, 느낌점 등


---



# :pushpin: velo9
>블로그 서비스 '벨로그'를 벤치마킹한 개인용 블로그 서비스
>https://velo9.com  

</br>

## 1. 제작 기간 & 참여 인원
- 2022년 2월 21일 ~ 4월 16일
- 팀 프로젝트(5명)  
    - 백엔드: 김진욱 / 손찬우 / 김재민
    - 프런트엔드: 조민수 / 박찬하 

</br>

## 2. 사용 기술
#### `Back-end`
  - Java 8
  - Spring Boot 2.3
  - Gradle
  - Spring Data JPA
  - QueryDSL
  - MySQL 5.7
  - Spring Security
#### `Front-end`
  - React
  - Element UI

</br>

## 3. ERD 설계
![](https://zuminternet.github.io/images/portal/post/2019-04-22-ZUM-Pilot-integer/final_erd.png)


## 4. 핵심 기능
> velo9는 단순하고 직관적인 사용이 가능한 웹 기반 블로그 서비스입니다. <div>
> velo9는 블로그 활동에 필요한 다양한 편의 기능을 제공합니다.   
> 누구나 쉽고 간편하게 포스트 작성이 가능하며, 태그와 시리즈 정보를 활용해 포스트를 빠르게 탐색할 수 있습니다.

<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>

<div markdown="1">

## 4.1. 포스트 작성 관련 기능


> ### 4.1.1. MarkDown 미리보기 :pushpin: [코드 확인](www.naver.com)
  - 글 작성 시, MarkDown 문법이 적용된 포스트 결과물 미리보기를 지원합니다.
![](https://velog.velcdn.com/images/woply/post/5319c61f-512c-42bf-9546-9d7bb8f45f52/image.png)

<div>

> ### 4.1.2. 글 작성과 글 수정을 한 곳에서 처리 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/controller/PostController.java#L53)
  - 신규 글 작성과 기존 글 수정을 단일 'Controller - Service - Repository에서 처리할 수 있도록 코드를 설계하였습니다.   

<div>

> ### 4.1.3. 포스트 전용 섬네일 지원제목 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/api/PostThumbnailFileUploader.java#L37)
  - 포스트에 대한 정보를 한 눈에 확인 할 수 있도록 섬네일 업로드를 지원합니다.
![](https://velog.velcdn.com/images/woply/post/3431869a-6424-474b-8ba5-77a60294d134/image.png)   

<div>


> ### 4.1.4. 태그, 시리즈 등록 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/service/PostService.java#L61)
  - 포스트 내용을 쉽게 파악하고, 조회할 수 있도록 태그와 시리즈를 추가할 수 있습니다
![](https://velog.velcdn.com/images/woply/post/e1df9acb-8e18-4b68-a4fb-dc855e9b25d0/image.png)   

<div>

> ### 4.1.5. 포스트 소개글 자동 등록 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/dto/PostSaveDTO.java#L50)
  - 포스트 소개글 미입력시, 본문 내용의 150자를 소개글로 자동 등록합니다.  
<div>

> ### 4.1.6. 임시 저장 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/service/PostService.java#L169)
  - 작성 중인 포스트는 x분 마다 자동 저장됩니다.   

<div>

---



## 4.2. 포스트 조회 관련 기능


> ### 4.2.1. (메인 화면)멀티 검색 지원 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/domain/PostRepositoryCustomImpl.java#L150)
  - 메인 화면에서 키워드 검색 시, 포스트 내용과 태그 내용을 선택하여 검색할 수 있습니다.
![](https://velog.velcdn.com/images/woply/post/cc69fa55-8a5c-4f5f-a672-14154c30e681/image.png)

<div>

> ### 4.2.2. (메인 화면)정렬 조건 지원 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/controller/MainController.java#L36)
  - 메인 화면에서 포스트 조회 시, 원하는 정렬 조건을 설정하여 포스트 목록을 조회할 수 있습니다.
![](https://velog.velcdn.com/images/woply/post/b7b64377-ea3d-4c30-8601-1c5cb4617bfe/image.png)

<div>


> ### 4.2.3. (사용자 글 목록 화면) 태그, 시리즈 정보 기반 탐색 지원 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/domain/PostRepositoryCustomImpl.java#L34)
  - 포스트에 포함된 태그 정보와 시리즈 정보를 이용하여 관심있는 주제의 포스트를 탐색할 수 있습니다.
![](https://velog.velcdn.com/images/woply/post/558f94ca-e3e0-4617-a23d-b51d3362d30a/image.png)
![](https://velog.velcdn.com/images/woply/post/4584c209-1ab9-4225-bb38-a14636710791/image.png)

<div>



> ### 4.2.4. 포스트 상세 화면 - 이전 글, 다음 글 보기 지원  :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/domain/PostRepositoryCustomImpl.java#L116)
  - (동일한 시리즈 정보를 가지고 있거나, 등록된 순서를 기반으로) 현재 보고 있는 포스트의 이전 글과 다음 글을 보여 줍니다. 
![](https://velog.velcdn.com/images/woply/post/6a272958-1466-428c-a885-e8a580077b53/image.png)

<div>


> ### 4.2.5. 사용자 아카이브 - 좋아요, 최근 읽은 글 목록 지원 :pushpin: [코드 확인](https://github.com/team-express/velo9/blob/fb2cdc52f5a47e4bb1afaa4b15ce39540d57f85c/src/main/java/teamexpress/velo9/post/domain/PostRepositoryCustomImpl.java#L67)
  - 사용자가 '읽은 적'이 있는 모든 포스트와 '좋아요'를 누른 모든 포스트를 별도로 보여줍니다. 
![](https://velog.velcdn.com/images/woply/post/d50744ed-fd83-4f73-8501-8d8ce59d149c/image.png)

<div>

</div>
</details>

</br>

## 5. 핵심 트러블 슈팅
### 5.1. 컨텐츠 필터와 페이징 처리 문제
- 저는 이 서비스가 페이스북이나 인스타그램 처럼 가볍게, 자주 사용되길 바라는 마음으로 개발했습니다.  
때문에 페이징 처리도 무한 스크롤을 적용했습니다.

- 하지만 [무한스크롤, 페이징 혹은 “더보기” 버튼? 어떤 걸 써야할까](https://cyberx.tistory.com/82) 라는 글을 읽고 무한 스크롤의 단점들을 알게 되었고,  
다양한 기준(카테고리, 사용자, 등록일, 인기도)의 게시물 필터 기능을 넣어서 이를 보완하고자 했습니다.

- 그런데 게시물이 필터링 된 상태에서 무한 스크롤이 동작하면,  
필터링 된 게시물들만 DB에 요청해야 하기 때문에 아래의 **기존 코드** 처럼 각 필터별로 다른 Query를 날려야 했습니다.

<details>
<summary><b>기존 코드</b></summary>
<div markdown="1">

~~~java
/**
 * 게시물 Top10 (기준: 댓글 수 + 좋아요 수)
 * @return 인기순 상위 10개 게시물
 */
public Page<PostResponseDto> listTopTen() {

    PageRequest pageRequest = PageRequest.of(0, 10, Sort.Direction.DESC, "rankPoint", "likeCnt");
    return postRepository.findAll(pageRequest).map(PostResponseDto::new);
}

/**
 * 게시물 필터 (Tag Name)
 * @param tagName 게시물 박스에서 클릭한 태그 이름
 * @param pageable 페이징 처리를 위한 객체
 * @return 해당 태그가 포함된 게시물 목록
 */
public Page<PostResponseDto> listFilteredByTagName(String tagName, Pageable pageable) {

    return postRepository.findAllByTagName(tagName, pageable).map(PostResponseDto::new);
}

// ... 게시물 필터 (Member) 생략 

/**
 * 게시물 필터 (Date)
 * @param createdDate 게시물 박스에서 클릭한 날짜
 * @return 해당 날짜에 등록된 게시물 목록
 */
public List<PostResponseDto> listFilteredByDate(String createdDate) {

    // 등록일 00시부터 24시까지
    LocalDateTime start = LocalDateTime.of(LocalDate.parse(createdDate), LocalTime.MIN);
    LocalDateTime end = LocalDateTime.of(LocalDate.parse(createdDate), LocalTime.MAX);

    return postRepository
                    .findAllByCreatedAtBetween(start, end)
                    .stream()
                    .map(PostResponseDto::new)
                    .collect(Collectors.toList());
    }
~~~

</div>
</details>

- 이 때 카테고리(tag)로 게시물을 필터링 하는 경우,  
각 게시물은 최대 3개까지의 카테고리(tag)를 가질 수 있어 해당 카테고리를 포함하는 모든 게시물을 질의해야 했기 때문에  
- 아래 **개선된 코드**와 같이 QueryDSL을 사용하여 다소 복잡한 Query를 작성하면서도 페이징 처리를 할 수 있었습니다.

<details>
<summary><b>개선된 코드</b></summary>
<div markdown="1">

~~~java
/**
 * 게시물 필터 (Tag Name)
 */
@Override
public Page<Post> findAllByTagName(String tagName, Pageable pageable) {

    QueryResults<Post> results = queryFactory
            .selectFrom(post)
            .innerJoin(postTag)
                .on(post.idx.eq(postTag.post.idx))
            .innerJoin(tag)
                .on(tag.idx.eq(postTag.tag.idx))
            .where(tag.name.eq(tagName))
            .orderBy(post.idx.desc())
                .limit(pageable.getPageSize())
                .offset(pageable.getOffset())
            .fetchResults();

    return new PageImpl<>(results.getResults(), pageable, results.getTotal());
}
~~~

</div>
</details>

</br>

## 6. 그 외 트러블 슈팅
<details>
<summary>npm run dev 실행 오류</summary>
<div markdown="1">

- Webpack-dev-server 버전을 3.0.0으로 다운그레이드로 해결
- `$ npm install —save-dev webpack-dev-server@3.0.0`

</div>
</details>

<details>
<summary>vue-devtools 크롬익스텐션 인식 오류 문제</summary>
<div markdown="1">
  
  - main.js 파일에 `Vue.config.devtools = true` 추가로 해결
  - [https://github.com/vuejs/vue-devtools/issues/190](https://github.com/vuejs/vue-devtools/issues/190)
  
</div>
</details>

<details>
<summary>ElementUI input 박스에서 `v-on:keyup.enter="메소드명"`이 정상 작동 안하는 문제</summary>
<div markdown="1">
  
  - `v-on:keyup.enter.native=""` 와 같이 .native 추가로 해결
  
</div>
</details>

<details>
<summary> Post 목록 출력시에 Member 객체 출력 에러 </summary>
<div markdown="1">
  
  - 에러 메세지(500에러)
    - No serializer found for class org.hibernate.proxy.pojo.javassist.JavassistLazyInitializer and no properties discovered to create BeanSerializer (to avoid exception, disable SerializationConfig.SerializationFeature.FAIL_ON_EMPTY_BEANS)
  - 해결
    - Post 엔티티에 @ManyToOne 연관관계 매핑을 LAZY 옵션에서 기본(EAGER)옵션으로 수정
  
</div>
</details>
    
<details>
<summary> 프로젝트를 git init으로 생성 후 발생하는 npm run dev/build 오류 문제 </summary>
<div markdown="1">
  
  ```jsx
    $ npm run dev
    npm ERR! path C:\Users\integer\IdeaProjects\pilot\package.json
    npm ERR! code ENOENT
    npm ERR! errno -4058
    npm ERR! syscall open
    npm ERR! enoent ENOENT: no such file or directory, open 'C:\Users\integer\IdeaProjects\pilot\package.json'
    npm ERR! enoent This is related to npm not being able to find a file.
    npm ERR! enoent

    npm ERR! A complete log of this run can be found in:
    npm ERR!     C:\Users\integer\AppData\Roaming\npm-cache\_logs\2019-02-25T01_23_19_131Z-debug.log
  ```
  
  - 단순히 npm run dev/build 명령을 입력한 경로가 문제였다.
   
</div>
</details>    

<details>
<summary> 태그 선택후 등록하기 누를 때 `object references an unsaved transient instance - save the transient instance before flushing` 오류</summary>
<div markdown="1">
  
  - Post 엔티티의 @ManyToMany에 영속성 전이(cascade=CascadeType.ALL) 추가
    - JPA에서 Entity를 저장할 때 연관된 모든 Entity는 영속상태여야 한다.
    - CascadeType.PERSIST 옵션으로 부모와 자식 Enitity를 한 번에 영속화할 수 있다.
    - 참고
        - [https://stackoverflow.com/questions/2302802/object-references-an-unsaved-transient-instance-save-the-transient-instance-be/10680218](https://stackoverflow.com/questions/2302802/object-references-an-unsaved-transient-instance-save-the-transient-instance-be/10680218)
   
</div>
</details>    

<details>
<summary> JSON: Infinite recursion (StackOverflowError)</summary>
<div markdown="1">
  
  - @JsonIgnoreProperties 사용으로 해결
    - 참고
        - [http://springquay.blogspot.com/2016/01/new-approach-to-solve-json-recursive.html](http://springquay.blogspot.com/2016/01/new-approach-to-solve-json-recursive.html)
        - [https://stackoverflow.com/questions/3325387/infinite-recursion-with-jackson-json-and-hibernate-jpa-issue](https://stackoverflow.com/questions/3325387/infinite-recursion-with-jackson-json-and-hibernate-jpa-issue)
        
</div>
</details>  
    
<details>
<summary> H2 접속문제</summary>
<div markdown="1">
  
  - H2의 JDBC URL이 jdbc:h2:~/test 으로 되어있으면 jdbc:h2:mem:testdb 으로 변경해서 접속해야 한다.
        
</div>
</details> 
    
<details>
<summary> 컨텐츠수정 모달창에서 태그 셀렉트박스 드랍다운이 뒤쪽에 보이는 문제</summary>
<div markdown="1">
  
   - ElementUI의 Global Config에 옵션 추가하면 해결
     - main.js 파일에 `Vue.us(ElementUI, { zIndex: 9999 });` 옵션 추가(9999 이하면 안됌)
   - 참고
     - [https://element.eleme.io/#/en-US/component/quickstart#global-config](https://element.eleme.io/#/en-US/component/quickstart#global-config)
        
</div>
</details> 

<details>
<summary> HTTP delete Request시 개발자도구의 XHR(XMLHttpRequest )에서 delete요청이 2번씩 찍히는 이유</summary>
<div markdown="1">
  
  - When you try to send a XMLHttpRequest to a different domain than the page is hosted, you are violating the same-origin policy. However, this situation became somewhat common, many technics are introduced. CORS is one of them.

        In short, server that you are sending the DELETE request allows cross domain requests. In the process, there should be a **preflight** call and that is the **HTTP OPTION** call.

        So, you are having two responses for the **OPTION** and **DELETE** call.

        see [MDN page for CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS).

    - 출처 : [https://stackoverflow.com/questions/35808655/why-do-i-get-back-2-responses-of-200-and-204-when-using-an-ajax-call-to-delete-o](https://stackoverflow.com/questions/35808655/why-do-i-get-back-2-responses-of-200-and-204-when-using-an-ajax-call-to-delete-o)
        
</div>
</details> 

<details>
<summary> 이미지 파싱 시 og:image 경로가 달라서 제대로 파싱이 안되는 경우</summary>
<div markdown="1">
  
  - UserAgent 설정으로 해결
        - [https://www.javacodeexamples.com/jsoup-set-user-agent-example/760](https://www.javacodeexamples.com/jsoup-set-user-agent-example/760)
        - [http://www.useragentstring.com/](http://www.useragentstring.com/)
        
</div>
</details> 
    
<details>
<summary> 구글 로그인으로 로그인한 사용자의 정보를 가져오는 방법이 스프링 2.0대 버전에서 달라진 것</summary>
<div markdown="1">
  
  - 1.5대 버전에서는 Controller의 인자로 Principal을 넘기면 principal.getName(0에서 바로 꺼내서 쓸 수 있었는데, 2.0대 버전에서는 principal.getName()의 경우 principal 객체.toString()을 반환한다.
    - 1.5대 버전에서 principal을 사용하는 경우
    - 아래와 같이 사용했다면,

    ```jsx
    @RequestMapping("/sso/user")
    @SuppressWarnings("unchecked")
    public Map<String, String> user(Principal principal) {
        if (principal != null) {
            OAuth2Authentication oAuth2Authentication = (OAuth2Authentication) principal;
            Authentication authentication = oAuth2Authentication.getUserAuthentication();
            Map<String, String> details = new LinkedHashMap<>();
            details = (Map<String, String>) authentication.getDetails();
            logger.info("details = " + details);  // id, email, name, link etc.
            Map<String, String> map = new LinkedHashMap<>();
            map.put("email", details.get("email"));
            return map;
        }
        return null;
    }
    ```

    - 2.0대 버전에서는
    - 아래와 같이 principal 객체의 내용을 꺼내 쓸 수 있다.

    ```jsx
    UsernamePasswordAuthenticationToken token =
                    (UsernamePasswordAuthenticationToken) SecurityContextHolder
                            .getContext().getAuthentication();
            Map<String, Object> map = (Map<String, Object>) token.getPrincipal();

            String email = String.valueOf(map.get("email"));
            post.setMember(memberRepository.findByEmail(email));
    ```
        
</div>
</details> 
    
<details>
<summary> 랭킹 동점자 처리 문제</summary>
<div markdown="1">
  
  - PageRequest의 Sort부분에서 properties를 "rankPoint"를 주고 "likeCnt"를 줘서 댓글수보다 좋아요수가 우선순위 갖도록 설정.
  - 좋아요 수도 똑같다면..........
        
</div>
</details> 
    
</br>

## 6. 회고 / 느낀점
>프로젝트 개발 회고 글: https://www.회고글_링크.com