# 한국주소API (KoreaAddressAPI)
한국 주소 API, juso.go.kr의 주소데이터 기반으로 만든 한국주소 API입니다.

아래와 같은 다양한 형태의 주소를 깨끗한 주소로 만들어주는 API로, R 과 Python을 사용하여 개발되었습니다.

사용법은 [여기](아직링크없다)를 참고하세요

---
입력주소 예제 #1 도로명주소로 입력되어 있는 주소 예제입니다.

* 특정지역명이 여러가지로 작성된 주소 / 서울/ 서울시/ 서울특별시
* 주소 중간에 필요없는 문자나 특수문자가 추가되어 있음


- 서울 관악구 남현3길 78, 덕원빌딩 6층
- 서울특별시, 관악구 남현3길, 78 덕원빌딩 6층
- 서울시 관악구 남현3길 78 덕원빌딩 6층

출력주소 예제 #1

|시/도|군/구|도로명 주소|건물이름|호수/상세위치|
|---|---|---|---|---|
|서울|관악구|남현3길 78|덕원빌딩|6층|

---

입력주소 예제 #2 지번 주소로 입력되어 있는 주소 예제입니다.

* 특정지역명이 여러가지로 작성된 주소 / 서울/ 서울시/ 서울특별시
* 지번주소에 '번지'와 같은 필요 없는 글자가 포함되어 있음


- 서울 관악구 남현동 602-1 6층
- 서울시 관악구 남현동 602-1 6층
- 서울특별시 관악 남현동 602-1번지 6층
- 서울특별시 관악 남현동 602-1 6층

출력주소 예제 #2

|시/도|군/구|동/읍/면|지번/리|건물이름|호수/상세위치|
|---|---|---|---|---|---|
|서울|관악구|남현동|602-1|   |6층|

---

입력주소 예제 #3 동/읍/면과 도로명 주소가 함께 입력되어 있는 주소 예제입니다.

* 도로명주소와 함께, 동/읍/면이 함께 포함되어 있음


- 서울특별시 관악구 남현동 남현3길 78 6층

출력주소 예제 #3

***어케 하는게 좋을려나, 고민중***

# 프로젝트를 시작하게된 이유는..?
이 책으로 ↓ [DAT스터디](https://skysign.github.io/DAT/)를 진행하고 있었습니다. <br>
https://book.naver.com/bookdb/book_detail.nhn?bid=12256508

* 서로 열씸히 공부하였지만, 아직 R 코드는 익숙하지 않았어요
* R 코딩이 익숙하지 않아, 큰 데이터를 다루는게 힘들었어요
* Data Analysis는 아주 큰 데이터를 다뤄야 하는 **숙명**이 있습니다.
* 그러면, '데이터는 아주 큰대, 사람이 읽기 쉬운 데이터로 프로젝트를 하면 어떨까?'
* '그런 데이터가 뭐가 있을까?'
* 고민을 거듭한 끝에, '주소데이터가 우리에게 적합하겠구나!'

## 한국주소 rest API가 있지 않을까?
한국주소 rest API가 없다는걸 최근에 알게 되었어요.
* 다음에서 제공하는 주소API는 매우 좋지만, rest API가 없어요. 자세한 내용은 [여기 참고](https://github.com/daumPostcode/QnA#4-rest-api%EB%A1%9C%EB%8F%84-%EC%A0%9C%EA%B3%B5%ED%95%98%EA%B3%A0-%EC%9E%88%EB%82%98%EC%9A%94)하세요
* Toast 에서도 한국주소 API는 판매가 중지 되었습니다. 자세한 내용은 [여기 참고](https://www.toast.com/kr/support/notice/detail/1331)하세요
* juso.go.kr에서 제공하는 rest API가 있기는 했지만, 사용자가 입력한 에러가 있는 주소를 잘 처리해주지 못했습니다.

**결론! 없으면 만든다. :-)**

---

# 만든 사람들
한국주소API(KoreaAddressAPI)는 DAT스터디에서 개발하였습니다.
 https://skysign.github.io/DAT ← 여기 참고하세요

---

# 데이터 출처
이 프로젝트에 사용된 모든 주소/도로명/건물/상세주소 등의 데이터는 http://www.juso.go.kr/ 에서 제공하는 데이터를 사용하였습니다.

---