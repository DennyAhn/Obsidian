
JSON은 **JavaScript Object Notation**의 줄임말로 JavaScript 객체들을 나타내는 데이터의 대표적인 표현 기법이다.

예시) 
	"PEOPLE":[

	{"neme":"FREEMOA", "age": 28},

	]
	
호출 한 정보를 Javascript 를 활용하여 사용할 수 있도록 "파싱"하는 과정을 거치며 "PEOPLE" 이라는 객체가 가지고 있는 "FREEMOA", 28 이라는 데이터를 사용 할 수 있게 된다.


JSON(JavaScript Object Notation) 파싱은 JSON 형식의 문자열 데이터를 JavaScript에서 사용할 수 있는 객체로 변환하는 과정입니다. 이 과정을 통해 웹 서버와 클라이언트 간에 주고받은 데이터를 웹 페이지에서 직접적으로 다룰 수 있게 됩니다. JSON은 경량의 데이터 교환 형식으로, 텍스트 기반의 구조를 가지며 인간이 읽기 쉬우면서도 기계가 파싱하고 생성하기에 용이합니다.

### JSON 파싱의 필요성

- 서버로부터 받은 JSON 문자열 데이터를 웹 애플리케이션에서 활용하기 위해 JavaScript 객체로 변환해야 합니다.
- 데이터의 저장, 검색, 수정 등을 용이하게 하기 위해 구조화된 데이터 형식으로의 변환이 필요합니다.

### JSON 파싱 방법

JavaScript에서 JSON 파싱을 위한 기본적인 방법은 `JSON.parse()` 메소드를 사용하는 것입니다. 이 메소드는 JSON 문자열을 받아 JavaScript 객체로 변환합니다. 반대로, JavaScript 객체를 JSON 문자열로 변환할 때는 `JSON.stringify()` 메소드를 사용합니다.

### 예시

예를 들어, 다음과 같은 JSON 문자열이 있다고 가정합시다:

jsonCopy code

`{   "PEOPLE": [     {"name": "FREEMOA", "age": 28}   ] }`

이 JSON 문자열을 파싱하여 JavaScript 객체로 변환하고 사용하는 방법은 아래와 같습니다:

javascriptCopy code

`const jsonString = '{"PEOPLE":[{"name": "FREEMOA", "age": 28}]}'; const jsonObject = JSON.parse(jsonString);  console.log(jsonObject.PEOPLE[0].name); // 출력: FREEMOA console.log(jsonObject.PEOPLE[0].age); // 출력: 28`

여기서 `JSON.parse()` 메소드는 JSON 문자열을 JavaScript 객체로 변환하며, 변환된 객체에서 데이터를 접근하여 사용할 수 있습니다.

### 결론

JSON 파싱은 데이터 교환과 웹 개발에서 중추적인 역할을 합니다. 이를 통해 개발자는 서버와 클라이언트 간에 효율적으로 데이터를 주고받고, 웹 애플리케이션에서 쉽게 데이터를 다룰 수 있습니다. JSON의 경량성과 높은 호환성 덕분에 웹 개발뿐만 아니라 다양한 소프트웨어 개발 분야에서도 널리 사용되고 있습니다.