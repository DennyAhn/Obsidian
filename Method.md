
Method는 서버에서 특정 resourse를 조회하기 위해 사용되는데 여기서 "resourse"란 웹 페이지, 이미지, 데이터 등 인터넷을 통해 접근할 수 있는 모든 종류의 콘텐츠를 의미한다. 따라서 Method는 웹 서버와 클라이언트 간의 상호작용 방식을 결정한다고 보면 된다.

### 1. GET의 주요 특징

- **데이터 검색**: `GET` 메소드는 주로 데이터를 검색하거나 조회할 때 사용됩니다. 
- **데이터 전송 방식**: 요청 시, 데이터는 URL의 일부로서 된다. 예시: `https://example.com/api/users?user_id=123`과 같이 쿼리 스트링(`?user_id=123`)을 사용하여 데이터를 서버로 전송한다.
- **캐싱 가능**: `GET` 요청의 결과는 캐싱될 수 있어, 같은 요청이 반복될 때 서버의 부하를 줄이고 응답 속도를 빠르게 할 수 있다.
- **이력 남김**: `GET` 요청은 브라우저의 히스토리에 기록되며, 북마크에 추가 가능하며 이는 사용자가 특정 상태의 웹 페이지를 쉽게 저장하고 공유할 수 있게 해준다.
- **제한적 데이터 길이**: URL의 길이에는 제한이 있기 때문에, `GET` 요청을 통해 전송할 수 있는 데이터의 양에는 한계가 있고 따라서 대용량 데이터를 전송할 때는 `POST` 메소드를 사용하는 것이 좋습니다.

### 사용 사례

- **웹 사이트 조회**: 웹 브라우저가 웹 페이지를 불러올 때 `GET` 요청을 사용한다.
- **API를 통한 데이터 조회**: RESTful API에서 특정 자원의 정보를 조회할 때 `GET` 메소드를 사용합니다. 예를 들어, 사용자 프로필 정보, 게시글 목록 등을 조회할 때 해당 자원의 URL에 `GET` 요청을 보낸다.

### 2. POST

- **용도**: 서버에 데이터를 전송하여 새로운 자원을 생성할 때 사용됩니다. 예를 들어, 새로운 게시글을 작성하거나 가입 양식을 제출할 때 `POST` 메소드가 사용됩니다.
- **데이터 전송**: 데이터는 요청 본문(request body)을 통해 전송되며, URL에 데이터가 노출되지 않아 `GET` 메소드보다 보안적으로 안전합니다.
- **캐싱 및 이력**: 일반적으로 `POST` 요청의 결과는 캐싱되지 않으며, 브라우저 히스토리에 저장되지 않아 새로 고침 시 동일한 요청을 재전송하는 경고가 발생할 수 있습니다.

### 3. PUT

- **용도**: 서버에 있는 자원의 전체를 교체하기 위해 사용됩니다. 예를 들어, 사용자 프로필 정보를 업데이트할 때 `PUT` 메소드를 사용할 수 있습니다.
- **데이터 전송**: `POST` 메소드와 마찬가지로 데이터는 요청 본문을 통해 전송됩니다.
- **멱등성**: `PUT` 요청은 멱등(idempotent) 특성을 가집니다. 즉, 동일한 `PUT` 요청을 여러 번 수행해도 결과가 동일합니다.

### 4. DELETE

- **용도**: 서버의 특정 자원을 삭제할 때 사용됩니다.
- **멱등성**: `DELETE` 메소드도 멱등성을 가지며, 동일한 요청을 여러 번 수행해도 동일한 자원에 대한 최초의 삭제 요청 이후에는 변화가 없습니다.

### 5. PATCH

- **용도**: 서버에 있는 자원의 일부를 수정하기 위해 사용됩니다. 예를 들어, 사용자의 이메일 주소만 업데이트할 때 `PATCH` 메소드를 사용할 수 있습니다.
- **데이터 전송**: 변경하고자 하는 데이터만 요청 본문에 포함시켜 전송합니다.
- **멱등성**: `PATCH` 메소드는 수행될 때마다 다른 결과를 초래할 수 있으므로 멱등성이 보장되지 않을 수 있습니다.

### 6. OPTIONS

- **용도**: 서버가 지원하는 메소드를 조회할 때 사용됩니다. 예를 들어, 특정 URL에 대해 `OPTIONS` 요청을 보내면 해당 URL에서 사용할 수 있는 HTTP 메소드 목록을 반환받을 수 있습니다.
- **크로스 오리진 리소스 공유 (CORS)**: 웹 애플리케이션에서 다른 도메인의 리소스를 요청할 때, `OPTIONS` 메소드는 사전 요청(pre-flight request)으로 사용되어 해당 요청이 안전한지 서버에 확인합니다.


|Method|Purpose|Data Transmission|Idempotent|Cached|
|---|---|---|---|---|
|GET|Retrieve data from the server.|Data sent in URL parameters.|Yes|Yes, responses can be cached.|
|POST|Submit data to the server to create a new resource.|Data sent in request body.|No|No, responses are not typically cached.|
|PUT|Replace an existing resource on the server.|Data sent in request body.|Yes|No, responses are not typically cached.|
|DELETE|Delete a resource from the server.|N/A (No data typically sent).|Yes|No, responses are not typically cached.|
|PATCH|Apply partial modifications to a resource.|Only changes sent in request body.|No (can be but not guaranteed)|No, responses are not typically cached.|
|OPTIONS|Retrieve server-supported HTTP methods for a specific resource.|N/A (No data sent, used to retrieve information).|Yes|Yes, responses can be cached.|

|Method|Purpose|Data Transmission|Idempotent|Cached|
|---|---|---|---|---|
|GET|서버에서 데이터를 검색합니다.|URL 파라미터에 데이터가 전송됩니다.|예|예, 응답은 캐싱될 수 있습니다.|
|POST|서버에 데이터를 제출하여 새로운 자원을 생성합니다.|요청 본문에 데이터가 전송됩니다.|아니오|아니오, 응답은 일반적으로 캐싱되지 않습니다.|
|PUT|서버의 기존 자원을 교체합니다.|요청 본문에 데이터가 전송됩니다.|예|아니오, 응답은 일반적으로 캐싱되지 않습니다.|
|DELETE|서버에서 자원을 삭제합니다.|N/A (일반적으로 데이터가 전송되지 않습니다.)|예|아니오, 응답은 일반적으로 캐싱되지 않습니다.|
|PATCH|자원에 부분적 수정을 적용합니다.|요청 본문에 변경사항만 전송됩니다.|아니오(보장되지 않음)|아니오, 응답은 일반적으로 캐싱되지 않습니다.|
|OPTIONS|특정 리소스에 대해 서버가 지원하는 HTTP 메소드를 검색합니다.|N/A (정보를 검색하기 위해 사용되므로 데이터 전송 없음)|예|예, 응답은 캐싱될 수 있습니다.|