# [스터디] 웹 접근성

## 목적

팀 내 개발 시에 작성한 컴포넌트에 대한 검증을 위해 스토리북을 이용하여 화면 테스트를 작성하고 있다.
이때 화면에 노출된 요소 확인을 위한 요소 탐색을 위해 [쿼리 함수](https://testing-library.com/docs/queries/about)를 사용한다.
쿼리 함수는 [testing-library에서 권장하는 우선순위](https://testing-library.com/docs/queries/about#priority)를 참고하여 필요에 맞게 선택하여 사용하고 있다.

> 1. 누구나 접근 가능한 쿼리
> 2. 의미적 쿼리
> 3. 테스트 ID

위에서 언급한 우선순위의 `1`,`2`는 웹 접근성과 밀접한 연관이 있다. 그러므로 웹 접근성에 맞게 컴포넌트를 작성하여야 하나 웹 접근성에 대한 명확한 이해가 없어 컴포넌트 작성 시에 웹 접근성에 맞게 작성하고 있는 것인지에 대한 확신이 없는 상황이다.
이를 해소하기 위해 웹 접근성이 무엇인지, 브라우저에서 어떻게 해석이 되는지, 어떤 규칙에 맞게 작성하여야 하는지에 대해 알아보려고 한다.

## 스터디 진행

- [W3C 홈페이지](https://www.w3.org/WAI/)에 작성된 웹 접근성 관련 글을 교재로 사용한다.

### 스터디 진행 방법

1. 주차별로 해당 링크의 내용을 읽고 각자 내용을 요약 정리한다.
2. 정리한 내용은 각 주차별 위키의 댓글로 남긴다.
3. 매주 화요일에 모여 정리한 내용을 기반으로 회고를 진행한다.
   - 해당 주차에서 읽고 느낀 부분
   - 인상 깊었던 부분
   - 논의 해볼만한 부분
   - 참고하면 좋을 부분
     - 개인적으로 찾아보고 이해하기 좋았던 블로그
     - W3C 이외에도 웹 접근성 관련에 대해 잘 정리된 웹사이트

## 스터디 일정

| 주차-날짜    | 주제                                                                                                                                                                                                                                                |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1주차 - 7/23 | [웹 접근성 소개](https://www.w3.org/WAI/fundamentals/accessibility-intro/ko)<br>[웹 접근성 원칙](https://www.w3.org/WAI/fundamentals/accessibility-principles/ko)                                                                                   |
| 2주차 - 7/30 | [Tip for Writing](https://www.w3.org/WAI/tips/writing/)<br>[Tip for Designing](https://www.w3.org/WAI/tips/designing/)<br>[Tip for Developing](https://www.w3.org/WAI/tips/developing/)<br>[Audio & Vidio Media](https://www.w3.org/WAI/media/av/)? |
| 3주차 - 8/6  | [Tutorial - Page Structure](https://www.w3.org/WAI/tutorials/page-structure/)                                                                                                                                                                       |
| 4주차 - 8/13 | [Tutorial - Menus](https://www.w3.org/WAI/tutorials/menus/)                                                                                                                                                                                         |
| 5주차 - 8/20 | [Tutorial - Images](https://www.w3.org/WAI/tutorials/images/)                                                                                                                                                                                       |
| 6주차 - 8/27 | [Tutorial - Tables](https://www.w3.org/WAI/tutorials/tables/)                                                                                                                                                                                       |
| 7주차 - 9/3  | [Tutorial - Forms](https://www.w3.org/WAI/tutorials/forms/)                                                                                                                                                                                         |
| 8주차 - 9/10 | [Tutorial - Carousels](https://www.w3.org/WAI/tutorials/carousels/)                                                                                                                                                                                 |
