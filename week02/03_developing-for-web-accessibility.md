# [Developing for Web Accessibility](https://www.w3.org/WAI/tips/developing/)

## 모든 폼 컨트롤에 레이블을 연결하라

- 폼 요소의 id 속성에 연결된 레이블 요소에 for 속성을 사용하거나 WAI-ARIA 속성을 사용

## 이미지에 대체 텍스트 포함하라

- 장식용 이미지의 경우 `alt=""`를 사용하거나 CSS로 처리

## 페이지 언어 및 언어 변경 사항을 식별하라

- `html` 태그에 `lang` 속성을 사용하여 모든 페이지의 기본 언어를 표시(ex: `<html lang="en">`)
- 특정 요소의 언어가 페이지의 나머지 언어와 다른 경우 특정 요소에 `lang` 속성을 사용

## 마크업으로 의미와 구조를 전달하라

- `<nav>` 및 `<aside>`와 같은 시멘틱 요소 활용
- WAI-ARIA 역할 활용(ex: `role="search"`)

## 사용자가 실수를 방지하고 수정할 수 있게 지원하라

- 사용자 입력을 처리할 때 가능한 한 형식에 관대해야 한다.

## 코드 순서에 읽기 순서 반영

- 코드 내 요소의 순서가 제시된 정보의 논리적 순서와 일치해야 함

## 사용자의 기술에 맞게 코드를 작성하라

- 반응형 디자인
- 글꼴 크기를 200% 이상으로 늘려도 스크롤, 내용 잘림이 없어야 함
- [점진적 향상](https://developer.mozilla.org/ko/docs/Glossary/Progressive_Enhancement)

## 비표준 대화형 요소에 대한 의미를 제공하라

- 아코디언 및 사용자 지정 버튼
- 사용자 지정 위젯의 기능 및 상태에 대한 정보를 제공하려면 WAI-ARIA를 사용
  - ex: `role="navigation"`, `aria-expanded="true"`

## 모든 대화형 요소가 키보드로 접근할 수 있게 하라

- 메뉴, 마우스오버에 반응하는 정보, 아코디언, 미디어 플레이어와 같은 대화형 요소를 개발할 때 키보드 접근성을 고려해야 함
- `tabindex="0"`

## 가능하면 보안 문자를 쓰지 말라

- CAPTCHA의 대안
  - 자동 감지
  - 인터페이스 상호작용
- 꼭 써야 한다면,
  - 두 가지 이상 해결 방법 제공
  - CAPTCHA를 우회할 수 있는 담당자 액세스 권한 제공
  - 권한이 부여된 사용자에게 CAPTCHA를 요구하지 않음
