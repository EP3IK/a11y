# [이미지 튜토리얼](https://www.w3.org/WAI/tutorials/images/)

## [이미지, 왜 중요할까?](https://www.w3.org/WAI/tutorials/images/#why-is-this-important)

이미지와 그래픽은 많은 사람들, 특히 인지 및 학습 장애가 있는 사람들이 콘텐츠를 더 즐겁고 쉽게 이해할 수 있도록 도와준다.
저시력자를 비롯한 시각 장애가 있는 사람들이 콘텐츠에서 방향을 잡는 데 사용하는 단서 역할을 한다.

하지만 이미지는 웹사이트에서 광범위하게 사용되며 접근성이 떨어지면 큰 장벽이 될 수 있다. 접근성이 좋은 이미지는 다음과 같은 여러 상황에서 유용하다.

- **스크린 리더 사용자**: 대체 텍스트는 소리내어 읽거나 점자로 렌더링할 수 있다.
- **음성 입력 소프트웨어 사용자**: 사용자는 한 번의 음성 명령으로 버튼이나 링크가 있는 이미지로 포커스를 보낼 수 있다.
- **음성 지원 웹사이트를 탐색하는 사람들**: 대체 텍스트를 소리내어 읽을 수 있다.
- **모바일 웹 사용자**: 특히 데이터 로밍 시에 이미지를 차단할 수 있다.
- **검색 엔진 최적화**: 검색 엔진에서 이미지를 색인화할 수 있다.

> 참고
>
> 웹사이트에서 이미지를 제거하면(텍스트 전용 버전) 이러한 사용자가 또는 상황에서 웹사이트의 접근성과 기능이 떨어진다.

## [정보 제공 이미지](https://www.w3.org/WAI/tutorials/images/informative/)

정보 제공 이미지는 짧은 구절이나 문장으로 표현할 수 있는 간단한 개념이나 정보를 전달한다.
대체 텍스트는 일반적으로 이미지의 문자 그대로의 설명이 아닌 시각적으로 표시되는 의미나 내용을 전달해야 한다.

일부 상황에서는 문자 그대로의 자세한 설명이 필요할 수 있지만, 이미지의 내용이 전달할 정보의 전부 또는 일부인 경우에만 해당한다.
이미지를 필요한 정보로 볼지 장식으로 볼지는 작성자가 페이지에 이미지를 집어넣는 이유에 따라 판단한다.

### [예제 1: 다른 정보에 레이블을 지정하는 데 사용되는 이미지](https://www.w3.org/WAI/tutorials/images/informative/#example-1-images-used-to-label-other-information)

이 예제에서는 전화기 아이콘과 팩스 아이콘 두 개가 있다.
각 이미지 뒤에는 전화 번호가 있다.
시각적으로 보이는 것과 일관되게 "전화:" 및 "팩스:"라는 대체 텍스트가 각 번호와 연결된 장치를 식별하는 데 사용된다.

예제

<p>
  <img src="https://www.w3.org/WAI/content-images/tutorials/images/phone.png" alt="전화:"> 0123 456 7890
</p>
<p>
  <img src="https://www.w3.org/WAI/content-images/tutorials/images/fax.png" alt="팩스:"> 0123 456 7891
</p>

코드

```html
<p><img src="phone.png" alt="전화:" /> 0123 456 7890</p>
<p><img src="fax.png" alt="팩스:" /> 0123 456 7891</p>
```

### [예제 2: 다른 정보를 보완하는 데 사용되는 이미지](https://www.w3.org/WAI/tutorials/images/informative/#example-2-images-used-to-supplement-other-information)

다음 이미지는 방울이 달린 개를 보여준다.
이 이미지는 방울의 용도를 설명하는 옆의 텍스트를 보충한다.
시각적으로 보이지만 텍스트로 설명하지 않은 정보를 설명하는 데는 짧은 데체 텍스트로도 충분하다.
이 경우에 대체 텍스트는 "목줄에 방울이 달린 개."이다.

예제

<p>
  <img src="https://www.w3.org/WAI/content-images/tutorials/images/dog.jpg" alt="목줄에 방울이 달린 개.">
  Off-duty guide dogs often wear ...
</p>

코드

```html
<p>
  <img src="dog.jpg" alt="목줄에 방울이 달린 개." />
  Off-duty guide dogs often wear ...
</p>
```

> 참고
>
> 텍스트에 개가 방울을 착용하는 방법에 대한 설명이 포함된 경우 이미지는 중복이고 [장식](https://www.w3.org/WAI/tutorials/images/decorative/)인 것으로 간주할 수 있다.
> 여기서는 방법을 텍스트에 언급하지 않았기 때문에 이미지가 정보를 제공하는 것으로 간주한다.

### [예제 3: 간결한 정보를 전달하는 이미지](https://www.w3.org/WAI/tutorials/images/informative/#example-3-images-conveying-succinct-information)

이 간단한 다이어그램은 병뚜껑을 열 때 시계 반대 방향으로 돌린다는 것을 설명한다.
이 정보는 짧은 문장으로 설명할 수 있으므로 "뚜껑을 누르고 시계 반대 방향(오른쪽에서 왼쪽으로)으로 돌리세요"라는 대체 텍스트를 `alt` 속성에 넣을 수 있다.

예제

<img src="https://www.w3.org/WAI/content-images/tutorials/images/counter-clockwise.jpg" alt="뚜껑을 누르고 시계 반대 방향(오른쪽에서 왼쪽으로)으로 돌리세요">

코드

```html
<img
  src="https://www.w3.org/WAI/content-images/tutorials/images/counter-clockwise.jpg"
  alt="뚜껑을 누르고 시계 반대 방향(오른쪽에서 왼쪽으로)으로 돌리세요"
/>
```

> 참고
>
> 1. 또 다른 기법은 이미지에 대체 텍스트를 넣는 것 대신 주 콘텐츠 내에 지침을 제공하는 다른 방법도 있다. 이 방법은 모든 사람이 모든 정보를 텍스트로 볼 수 있도록 하는 동시에 시각적으로 정보를 접하는 걸

     선호하는 사람에게 그림을 제공한다.

> 2. 다이어그램보다 더 많은 정보를 이미지로 전달하려는 경우 [복잡한 이미지](https://www.w3.org/WAI/tutorials/images/complex/)에 설명된 방법 중 하나를 택하는 것이 더

     나을 수 있다. 예를 들어 이 다이어그램이 병에 표시되어 있다는 사실이나 병의 모양과 크기가 관련 정보인 경우에는 더 자세한 내용의 대체 텍스트를 사용해야 한다.

### [예제 4: 인상이나 감정을 전달하는 이미지](https://www.w3.org/WAI/tutorials/images/informative/#example-4-images-conveying-an-impression-or-emotion)

이 사진에는 행복한 가족이 있다.
이 사진은 스톡 이미지이므로 각자가 누군지 알 수 없다.
이 이미지는 웹사이트 또는 그 웹사이트가 대표하는 회사가 가족 친화적이라는 인상을 주는 용도로 사용한다.
대체 텍스트는 "우리는 가족 친화적입니다"로 하는 것이 의도한 인상을 가장 잘 설명할 수 있다.

예제

<img src="https://www.w3.org/WAI/content-images/tutorials/images/family.jpg" alt="우리는 가족 친화적입니다.">

코드

```html
<img src="family.jpg" alt="우리는 가족 친화적입니다." />
```

> 참고
>
> 이 이미지의 목적이 인상을 전달하는 것이 아니라 단순히 페이지를 더 낫게 보이게 하는
> 것이라면 ["장식 이미지: 분위기에 사용되는 이미지"](https://www.w3.org/WAI/tutorials/images/decorative/#image-used-for-ambiance-eye-candy)
> 에서처럼 장식으로 간주할 수 있다.
> 작성자가 이미지 사용 목적을 결정한다.

### [예제 5: 파일 형식을 전달하는 이미지](https://www.w3.org/WAI/tutorials/images/informative/#example-5-images-conveying-file-format)

이 예제에서는 문서를 텍스트 링크 내에 포맷 아이콘으로 식별되는 세 가지 포맷으로 다운로드할 수 있다.
포맷 아이콘은 각 링크의 파일 종류를 구분하기 위해 "HTML", "워드 문서", 그리고 "PDF"라는 대체 텍스트를 가진다.

예제

<p>
  <a href="…">
    2012 Annual report and accounts
    <img src="https://www.w3.org/WAI/content-images/tutorials/images/html5logo.png" alt="HTML" > (43KB)
  </a>, also available in
  <a href="…">
    <img src="https://www.w3.org/WAI/content-images/tutorials/images/worddocument.png" alt="워드 문서"> (254KB)
  </a>
  or
  <a href="…">
    <img src="https://www.w3.org/WAI/content-images/tutorials/images/pdfdocument.png" alt="PDF"> (353KB)
  </a>
  format.
</p>

코드

```html
<p>
  <a href="…">
    2012 Annual report and accounts
    <img src="html5logo.png" alt="HTML" /> (43KB) </a
  >, also available in
  <a href="…"> <img src="worddocument.png" alt="Word document" /> (254KB) </a>
  or
  <a href="…"> <img src="pdfdocument.png" alt="PDF" /> (353KB) </a>
  format.
</p>
```

> 참고
>
> 1. 포맷 식별이 링크 텍스트의 일부로 작성된 경우 이미지는 장식으로 간주되어 `alt` 속성이 비어있을(`alt=""`) 수 있다. 텍스트와 동일한 링크 요소(`<a>`)에 속해서 클릭 가능한 영역에 포함될 수

     있다. ["기능적 이미지: 링크 텍스트 내 로고 이미지"](https://www.w3.org/WAI/tutorials/images/functional/#logo-image-within-link-text)에서
     더 많은 내용이 있다.

> 2. 이번 예제는 이미지가 링크 텍스트에 없는 정보를 전달한다는

     점에서 [기능적 이미지: 링크 텍스트 내에서 정보를 전달하는 아이콘 이미지](https://www.w3.org/WAI/tutorials/images/functional/#example-3-icon-image-conveying-information-within-link-text)
     와 유사하다.

## [장식 이미지](https://www.w3.org/WAI/tutorials/images/decorative/)

장식 이미지는 페이지 콘텐츠에 정보를 추가하지 않는다.
예를 들어 이미지가 제공하는 정보가 이미 인접한 텍스트를 통해 제공되었거나 이미지가 웹사이트를 시각적으로 더 매력적으로 만들기 위해 포함될 수 있다.

이러한 경우 `alt` 속성이 비어있게(`alt=""`) 해야 스크린 리더 등의 보조 기술에서 이미지를 무시할 수 있다.
이러한 유형의 이미지에 있는 텍스트 값은 스크린 리더 출력에 청각적으로 혼란을 더할 수도 있고 이미지가 다루는 주제가 인접한 텍스트의 내용과 다른 경우 사용자의 주의를 분산시킬 수도 있다.
`alt` 속성을 제공하지 않으면 일부 스크린 리더가 이미지의 파일 이름을 대신 알리기 때문에 이 속성을 생략하는 것은 선택 사항이 아니다.

이미지를 장식으로 처리할지 [정보 제공용](https://www.w3.org/WAI/tutorials/images/informative/)으로 처리할지는 페이지에 이미지를 포함하는 이유에 따라 작성자만이 판단할 수
있는 것이다.
아래의 경우 이미지는 장식일 수 있다.

- 테두리, 간격, 모서리 등의 시각적 스타일링
- 링크 텍스트의 외관을 개선하거나 클릭 가능한 영역을 늘리기 위한 보조 요소
- 인접한 텍스트를 나타내지만 정보를 제공하지는 않는 요소("눈요기")
- 주변 텍스트로 식별 및 설명되는 요소

아래 예시에서는 `<img>` 요소를 사용하여 장식 이미지를 제공할 때 `alt` 속성을 사용하는 방법을 보여준다.
가능한 경우 장식 이미지는 CSS 배경 이미지를 대신 사용하여 제공해야 한다.

### [예제 1: 페이지 디자인의 일부로 사용되는 이미지](https://www.w3.org/WAI/tutorials/images/decorative/#example-1-image-used-as-part-of-page-design)

이 이미지는 페이지 디자인에서 테두리로 사용되며 순전히 장식 목적으로 사용된다.

예제

<img src="https://www.w3.org/WAI/content-images/tutorials/images/topinfo_bg.png" alt="">

코드

```html
<img src="topinfo_bg.png" alt="" />
```

스크린 리더에서는 WAI-ARIA의 `role="presentation"`을 사용하여 요소를 숨기는 것도 가능하다.
그러나 현재 이 기능은 `alt` 속성을 빈 값으로 만드는 걸 사용하는 것만큼 널리 지원되지는 않는다.

코드

```html
<img src="topinfo_bg.png" role="presentation" />
```

> 참고
>
> 이미지가 스토리의 장면 전환이나 다른 주제로의 전환 등 주제별 구분을 나타내는 데 사용되는 경우 보조 기술에서 변화를 알아차리도록 `<hr>` 요소를 사용하는 것이 적절할 수 있다.

### [예제 2: 텍스트 링크의 일부인 장식 이미지](https://www.w3.org/WAI/tutorials/images/decorative/#example-2-decorative-image-as-part-of-a-text-link)

이 크로커스 그림은 링크를 더 쉽게 식별하고 클릭 가능한 영역을 늘리기 위해 사용되지만 (같은 앵커에 있는) 인접한 링크 텍스트가 이미 제공하고 있는 정보에 추가하지는 않는다.
이 경우 이미지에 빈 `alt` 값을 사용한다.

예제

<a href="crocuspage.html">
  <img src="https://www.w3.org/WAI/content-images/tutorials/images/crocus.jpg" alt="">
  <strong> Crocus bulbs</strong>
</a>

코드

```html
<a href="crocuspage.html">
  <img src="crocus.jpg" alt="" />
  <strong> Crocus bulbs</strong>
</a>
```

### [예제 3: 대체 문구가 인접해 있는 이미지](https://www.w3.org/WAI/tutorials/images/decorative/#example-3-image-with-adjacent-text-alternative)

이 잠자는 개 그림은 이미 인접한 텍스트가 충분히 설명하고 있다.
이 정보를 반복할 필요가 없으며 이 이미지에 빈 `alt` 값을 사용할 수 있다.

예제

<p>
  <img src="https://www.w3.org/WAI/content-images/tutorials/images/sleeping.jpg" alt="">
  <strong>The sleeping dog:</strong> Let sleeping dogs lie is a proverb that means “don’t initiate trouble. If something that could be troublesome is quiet, then leave it alone”.
</p>

코드

```html
<p>
  <img src="sleepingdog.jpg" alt="" />
  <strong>The sleeping dog:</strong> ...
</p>
```

### [예제 4: 분위기에 사용되는 이미지(눈요기)](https://www.w3.org/WAI/tutorials/images/decorative/#example-4-image-used-for-ambiance-eye-candy)

이 이미지는 페이지에 분위기나 시각적 흥미를 더하는 용도로만 사용한다.

예제

<p>
<img src="https://www.w3.org/WAI/content-images/tutorials/images/kew.jpg" alt="">
  Don’t miss the impressive Tropical House – a huge greenhouse that displays examples of exotic plant-life from every tropical environment on the planet.
</p>

코드

```html
<img src="tropical.jpg" alt="" />
```

> 참고
>
> 이 이미지의 목적이 단순히 페이지의 외관을 개선하기 위한 것이 아니라 식물을 식별하거나 다른 정보를 전달하는
> 것이라면 [정보 제공](https://www.w3.org/WAI/tutorials/images/informative/)으로 간주해야 한다.
> 이미지의 사용 목적은 작성자가 결정한다.

## [기능적 이미지](https://www.w3.org/WAI/tutorials/images/functional/)

기능적 이미지는 정보를 전달하기보다는 행동을 유도하는 데 사용한다.
버튼, 링크 및 기타 상호작용 요소에 사용된다.
이미지의 대체 텍스트는 이미지에 대한 설명이 아니라 유도할 행동(이미지의 목적)을 전달해야 한다.

예를 들어 아래 예제와 같이 대체 텍스트는 "프린터(의 이미지)"가 아니라 "이 페이지 인쇄", "돋보기"가 아니라 "검색", "Example.com 로고"가 아니라 "Example.com 홈페이지"가 되어야 한다.

기능적 이미지는 콘텐츠의 기능에 반드시 필요하기 때문에 `alt` 값이 없거나 비어 있으면 스크린 리더 사용자에게 심각한 문제를 일으킬 수 있다.
스크린 리더는 일반적으로 이미지 파일 이름, 이미지 URL 또는 링크 대상의 URL을 알려주는데, 이는 사용자가 이미지로부터 시작할 작업을 이해하는 데 도움이 되지 않을 수 있다.

### [예제 1: 링크가 연결된 로고로써 단독으로 사용된 이미지](https://www.w3.org/WAI/tutorials/images/functional/#example-1-image-used-alone-as-a-linked-logo)

아래 이미지는 W3C 홈 페이지로 연결되는 링크의 유일한 콘텐츠이다.
이 이미지에는 링크가 사용자를 어디로 이동시키는지를 나타내기 위해 "W3C home"이라는 대체 텍스트가 있다.
다음 예제인 ["링크 텍스트 내 로고 이미지" 예제](https://www.w3.org/WAI/tutorials/images/functional/#logo-image-within-link-text)에서는 링크에
목적지를 식별하는 텍스트가 더 있는 경우 어떻게 해야 하는지를 다룬다.

예제

<a href="https://www.w3.org/">
  <img src="https://www.w3.org/WAI/content-images/tutorials/images/w3c.png" alt="W3C home">
</a>

코드

```html
<a href="https://www.w3.org/">
  <img src="w3c.png" alt="W3C home" />
</a>
```

> 참고
>
> 1. 이 경우 로고는 텍스트 "W3C"를 나타내는 이미지이기도 하지만 이 경우 로고의 주요 기능은 홈페이지로 연결하는 것이므로 대체 텍스트에 "home"이라는 단어를 추가했다.
> 2. 로고로 사용하는 이미지에는 다른 텍스트 이미지에 적용하는 최소 색상 대비 값, 텍스트 크기와 같은 일부 접근성 요구 사항을 면제 받는다.

### [예제 2: 링크 텍스트 내 로고 이미지](https://www.w3.org/WAI/tutorials/images/functional/#logo-image-within-link-text)

이 예제에서는 W3C 홈페이지로 가는 링크 내의 텍스트를 보완하는 데 W3C 로고를 사용한다.
이미지는 링크 텍스트가 이미 제공하는 것과 다른 기능을 나타내거나 다른 정보를 전달하지 않으므로 중복 및 반복을 방지하기 위해 빈 `alt` 값을 적용한다.
사실상 이미지는 링크 텍스트에 대한 장식적인 부속물 또는 시각적 단서이다.

예제

<a href="https://www.w3.org/">
  <img src="https://www.w3.org/WAI/content-images/tutorials/images/w3c.png" alt=""> W3C Home
</a>

코드

```html
<a href="https://www.w3.org/"> <img src="w3c.png" alt="" /> W3C Home </a>
```

### [예제 3: 링크 텍스트 내에서 정보를 전달하는 아이콘 이미지](https://www.w3.org/WAI/tutorials/images/functional/#example-3-icon-image-conveying-information-within-link-text)

이 예제에서는 링크 내의 텍스트 다음에 이미지가 위치하여 링크가 새 창에서 열릴 것임을 사용자에게 알린다.
아이콘의 의미를 전달하기 위해 '새 창'이라는 대체 텍스트가 있다.

예제

<a href="https://www.w3.org/" target="_blank">
    W3C Homepage <img src="https://www.w3.org/WAI/content-images/tutorials/images/new-window.png" alt="새 창">
</a>

코드

```html
<a href="https://www.w3.org/" target="_blank">
  W3C Homepage <img src="new-window.png" alt="새 창" />
</a>
```

### [예제 4: 기능이 있는 독립형 아이콘 이미지](https://www.w3.org/WAI/tutorials/images/functional/#example-4-stand-alone-icon-image-that-has-a-function)

아래 이미지는 인쇄 기능을 나타내는 프린터 아이콘이다.
이 아이콘을 선택하면 인쇄 대화 상자를 활성화하는 것이 목적이므로 "이 페이지 인쇄"라는 대체 텍스트가 있다.

예제

<a href="https://www.w3.org/" target="_blank">
    W3C Homepage <img src="https://www.w3.org/WAI/content-images/tutorials/images/new-window.png" alt="새 창">
</a>

코드

```html
<a href="javascript:print()">
  <img
    src="https://www.w3.org/WAI/content-images/tutorials/images/print.png"
    alt="Print this page"
  />
</a>
```

### [예제 5: 버튼에 사용된 이미지](https://www.w3.org/WAI/tutorials/images/functional/#example-5-image-used-in-a-button)

아래 이미지는 버튼에 고유한 스타일을 부여하는 데 사용한다.
이 경우 이 버튼은 검색 요청을 시작하는 버튼이며 돋보기를 나타내는 아이콘이다.
이미지의 대체 텍스트는 버튼의 목적을 전달하기 때문에 "검색"이다.

예제

<input type="image" src="https://www.w3.org/WAI/content-images/tutorials/images/searchbutton.png" alt="검색">

코드

```html
<input type="image" src="searchbutton.png" alt="검색" />
```

## [텍스트 이미지](https://www.w3.org/WAI/tutorials/images/textual/)

텍스트 이미지는 읽을 수 있는 텍스트를 표시한다.
대부분의 웹 브라우저에서 현재 CSS 기능이 지원되므로 이미지 기반 텍스트를 표시하기보다는 CSS로 스타일을 지정한 실제 텍스트를 사용하는 것이 좋은 디자인이다.
실제 텍스트는 선명도를 떨어뜨리지 않고 크기를 조정할 수 있으며 사용자가 선호하는 읽기 환경에 맞게 배경 및 텍스트 색상을 수정할 수 있다는 점에서 이미지보다 훨씬 유연하다.
이미지는 크기를 조정하면 이미지가 왜곡되거나 픽셀화될 가능성이 높다.
드물지만 텍스트 이미지를 사용해야 하는 경우 대체 텍스트에는 이미지에 표시된 텍스트와 동일한 텍스트가 포함되어야 한다.

### [예제 1: 장식 효과가 있는 스타일링된 텍스트](https://www.w3.org/WAI/tutorials/images/textual/#styled-text-decorative-effect)

아래 이미지는 장식 효과가 있는 슬로건 텍스트를 전달하는 데 사용한다.

예제

<img src="https://www.w3.org/WAI/content-images/tutorials/images/bad-top-text.png" alt="Your access to the city.">

#### [이미지 사용](https://www.w3.org/WAI/tutorials/images/textual/#using-an-image)

이전에는 여러 브라우저에서 일관되게 렌더링되는 CSS 스타일링을 사용하여 이러한 텍스트를 만들 수 없었기 때문에 텍스트 이미지를 사용했다.
이 이미지의 대체 텍스트는 이미지에 표시된 슬로건("Your access to the city.")과 동일하다.
장식 효과(스타일을 입힌 텍스트와 그림자)는 관련이 없으므로 설명하지 않는다.

코드

```html
<img src="access-city.png" alt="Your access to the city." />
```

#### [CSS3 사용](https://www.w3.org/WAI/tutorials/images/textual/#using-css3)

위 이미지의 시각적 효과는 CSS3와 임베디드 글꼴을 사용하여 만들 수 있다.
구형 브라우저를 지원해야 하는 작성자와 개발자는 스타일이 덜 지정된 대체 텍스트를 사용할 수 없는 경우 이 이미지 예제가 유용할 수 있다.

코드: HTML

```html
<div class="tagline"><span>Your access to the city</span></div>
```

코드: CSS

```CSS
@font-face {
  font-family: 'Harabara Hand';
  src: url('harabarahand.ttf') format('truetype');
}

.background {
  background-color: #FFF;
  padding: 2em;
}
.tagline {
  font-family: 'Harabara Hand', cursive;
  text-transform: lowercase;
  color: #226C8E;
  font-size: 1.5em;
  letter-spacing: -1px;
  padding-left: 1em;
  background-color: #DDD9D6;
  box-shadow: 0 2px  4px rgba(0,0,0,.5);
}
.tagline span {
  display: inline-block;
  transform: rotate(-10deg);
}
```

> 참고
>
> 코드 스니펫에는 벤더 접두사("webkit-\*")가 없다.
> CSS3 기능의 실험적 구현을 사용하여 이전 버전의 웹 브라우저와의 호환성을 높이기 위해 이러한 접두사를 추가할 수 있다.

### [예제 2: 링크가 없는 로고로 사용된 텍스트 이미지](https://www.w3.org/WAI/tutorials/images/textual/#example-2-image-of-text-used-as-an-unlinked-logo)

다음 이미지는 웹 접근성 이니셔티브의 로고이다.
링크의 일부가 아니므로 대체 텍스트는 "웹 접근성 이니셔티브"입니다.
로고라는 점을 언급할 필요가 없다.

예제

<img src="https://www.w3.org/WAI/content-images/tutorials/images/wai.png" alt="웹 접근성 이니셔티브">

코드

```html
<img src="wai.png" alt="웹 접근성 이니셔티브" />
```

> 참고
>
> 1. 로고로 사용하는 이미지는 다른 텍스트 이미지에 적용되는 일부 접근성 요구 사항에서 제외된다. 예를 들어 최소 색상 대비 및 텍스트 크기 요구 사항이 없다.
> 2. 이 로고에 링크가 연결되면 기능적 이미지가

     된다. [기능적 이미지: 링크가 연결된 로고로써 단독으로 사용된 이미지](https://www.w3.org/WAI/tutorials/images/functional/#example-1-image-used-alone-as-a-linked-logo)
     에서 확인할 수 있다.

### [예제 3: 수학 표현식](https://www.w3.org/WAI/tutorials/images/textual/#example-3-mathematical-expressions)

지금까지 수학 표현은 방정식과 특수 수학 기호를 HTML로 표현하기 어렵기 때문에 이미지로 표시되는 경우가 많았다.
그러나 MathML이 웹에서 접근 가능한 수학을 표현하는 데 선호되는 방식으로 떠오르고 있다.

#### [이미지 사용](https://www.w3.org/WAI/tutorials/images/textual/#using-images)

아래 이미지는 무한 소수를 표시한다.
이 반복 숫자의 대체 텍스트는 "0.3333 반복(이미지에서 반복은 소수점 넷째 자리의 '3' 위에 줄을 그어 표시함)"이다.

이 특정 예제에서는 반복을 표시하는 방식이 중요하므로 대체 텍스트에도 설명되어 있다.
다른 이미지와 마찬가지로 작성자는 이미지가 전달하고자 하는 정보를 결정하고 그에 따라 데체 텍스트를 구성할 수 있는 가장 좋은 위치에 있다.

예제

![0.3333 반복(이미지에서 반복은 소수점 넷째 자리의 '3' 위에 줄을 그어 표시함)](https://www.w3.org/WAI/content-images/tutorials/images/repeat1.png)

코드

```html
<img
  src="0dot3333recurring.png"
  alt="0.3333 반복(이미지에서 반복은 소수점 넷째 자리의 '3' 위에 줄을 그어 표시함)"
/>
```

#### [MathML 사용](https://www.w3.org/WAI/tutorials/images/textual/#using-mathml)

수학 표현식 이미지는 표현식이 페이지 또는 웹사이트의 일반 콘텐츠에 대한 예외인 경우 와 같이 *예외적인 상황*에서만 사용해야 한다.
수학식을 표시하는 데 가장 선호되는 방법은 수학식을 의미적으로 표현할 수 있는 MathML이다.

수학식이 콘텐츠의 상당 부분을 차지하는 경우(예: 온라인 수학 강좌)에는 [MathML](https://www.w3.org/Math/)을 대신 사용해야 한다.
MathML은 표현과 내용을 의미론적으로 모두 보여주므로 더 많은 사용자가 더 쉽게 접근할 수 있다.

숫자를 반복하는 간단한 예제는 수학적 표현으로 내용과 표현을 간결하고 명확하게 설명하는 것이 얼마나 어려운지를 보여준다.
특히 반복를 나타내는 윗줄의 위치를 설명하는 것은 일부 수업 환경에 따라서는 중요하지만 번거롭다.
더 복잡한 표현식이나 방정식의 경우, 이미지의 대체 텍스트는 충분한 세부 정보를 간결하게 제공하지 못할 가능성이 높다.
MathML은 텍스트가 아닌 코드 내에서 이러한 시멘틱을 제공하는 데 도움이 된다.

코드

```html
<math>
  <mstack stackalign="right">
    <msline length="1" />
    <mn> 0.3333</mn>
  </mstack>
</math>
```

> 참고
>
> 위의 코드에는 보조 기술에 내용과 표현을 모두 전달하는 시맨틱 정보가 포함되어 있다.

## [복잡한 이미지](https://www.w3.org/WAI/tutorials/images/complex/)

복잡한 이미지에는 짧은 문구나 문장으로 전달할 수 있는 것보다 더 많은 정보가 담겨 있다.
일반적으로 다음과 같은 종류가 있다.

- 순서도 및 조직도를 포함한 그래프 및 차트
- 페이지 텍스트가 사용자의 이미지 이해 능력에 의존하는 다이어그램 및 일러스트레이션
- 기상 시스템과 같이 위치 또는 기타 정보를 표시하는 지도

이러한 경우 두 부분으로 구성된 대체 텍스트가 필요하다.
첫 번째 부분은 이미지를 식별하기 위한 짧은 설명이며, 필요한 경우 긴 설명의 위치를 표시한다.
두 번째 부분은 이미지가 전달하는 필수 정보를 텍스트로 표현한 긴 설명이다.
다음 예제에서는 이러한 짧은 설명과 긴 설명을 제공하는 데 사용할 수 있는 다양한 접근 방식을 보여준다.

### [긴 설명](https://www.w3.org/WAI/tutorials/images/complex/#long-descriptions)

이미지의 구성이 중요하여 긴 설명으로 제공해야 하는 경우가 있다.
예를 들어 막대 차트에서 사용된 색상의 순서와 열의 상대적 높이는 차트가 나타내는 실제 값과 추세 외에도 차트의 구조에 대한 관련 정보일 수 있다.

복잡한 이미지는 특히 저시력, 학습 장애, 주제에 대한 경험이 부족한 사람에게는 이해하기 어려울 수 있다.
더 많은 사람들에게 콘텐츠를 전달하려면 모든 사람이 긴 설명을 볼 수 있도록 해야 한다.
예를 들어 긴 설명을 주 콘텐츠의 일부로 표시하면 좋다.
또한 이미지에서 불필요하게 복잡한 것을 줄이고 누구나 이해하기 쉽게 만들 수도 있다.

첨부된 텍스트에서 더 복잡한 이미지를 참조하고 요약하는 것도 좋은 방법이다.
예를 들어 "다음 그래프는 1분기에는 방문자 수가 감소했지만 2분기에는 회복되었음을 보여줍니다."와 같은 참조는 이미지가 전달하고자 하는 관련 정보를 파악하는 데 도움이 된다.

### [예제 1: 구조화된 정보가 포함된 설명](https://www.w3.org/WAI/tutorials/images/complex/#example-1-description-containing-structured-information)

이 예제에서 웹사이트 방문자 통계를 나타내는 막대 차트에는 "사이트 1~3의 2014년 1분기 월별 및 총 방문자를 보여주는 막대 차트"라는 짧은 설명을 이미지의 `alt` 속성을 통해 제공한다.
긴 설명은 시각적으로 표현되는 척도, 값, 관계 및 추세를 포함한 자세한 정보를 제공한다.
예를 들어, 긴 설명은 막대 차트에 인코딩된 사이트 1의 감소하는 값, 사이트 2의 일관된 값, 사이트 3의 증가하는 값을 지적할 수 있다.
다음 예제에서
사용된 [longdesc 방법](https://www.w3.org/WAI/tutorials/images/complex/#approach-4-providing-a-link-to-the-long-description-via-longdesc)
은 이 섹션의 뒷부분에 설명되어 있다.

> 참고
>
> 아래 방식 중 첫 번째와 네 번째 방식은 웹 브라우저나 검색 엔진과 같은 다른 프로그램에서 정보를 사용할 수 있도록 한다.

#### [방법 1: 이미지 옆에 긴 설명으로 가는 텍스트 링크](https://www.w3.org/WAI/tutorials/images/complex/#approach-1-a-text-link-to-the-long-description-adjacent-to-the-image)

이 방법은 이미지 옆에 긴 설명이 포함된 별도의 웹 페이지 또는 동일한 웹 페이지의 섹션을 가리키는 텍스트 링크를 제공한다.
링크 텍스트는 목적지를 명확히 하고 이미지와 연결해야 한다.

코드

```html
<p>
  <img
    src="chart.png"
    alt="Bar chart showing monthly and total visitors for the first quarter 2014 for sites 1 to 3"
  />
  <br />
  <a href="2014-first-qtr.html"
    >Example.com Site visitors Jan to March 2014 text description of the bar
    chart</a
  >
</p>
```

이 접근 방식은 모든 웹 브라우저와 보조 기술에서 지원되며 모든 사람이 긴 설명을 사용할 수 있다.
그러나 링크는 의미론적으로 이미지와 연결되지 않는다.

HTML5 `<figure>` 및 `<figcaption>` 요소를 사용하여 이미지와 링크를 의미론적으로 그룹화할 수 있다.
그림에 `role="group"`을 추가하면 `<figure>` 요소의 기본 의미를 지원하지 않는 웹 브라우저와의 하위 호환성을 유지할 수 있다.

코드

```html
<figure role="group">
  <img
    src="chart.png"
    alt="Bar chart showing monthly and total visitors for the first quarter 2014 for sites 1 to 3"
  />
  <figcaption>
    <a href="2014-first-qtr.html"
      >Example.com Site visitors Jan to March 2014 text description of the bar
      chart</a
    >
  </figcaption>
</figure>
```

#### [방법 2: `alt` 속성에서 긴 설명의 위치를 설명](https://www.w3.org/WAI/tutorials/images/complex/#approach-2-describing-the-location-of-the-long-description-in-the-alt-attribute)

이미지와 동일한 웹 페이지에 긴 설명이 제공되는 경우 이미지의 `alt` 속성을 사용하여 위치를 설명할 수 있다.
위치 정보는 사용자가 콘텐츠를 찾는 데 도움이 되도록 명확하고 정확해야 한다.

```html
<p>
  <img
    src="chart.png"
    alt="Bar chart showing monthly and total visitors for the first quarter 2014 for sites 1 to 3. Described under the heading Site visitors full text."
  />
</p>
[…]
<h4>Site visitors full text</h4>
[…]
```

#### [방법 3: 이미지와 인접한 긴 설명을 구조적으로 연결(HTML5)](https://www.w3.org/WAI/tutorials/images/complex/#approach-3-structurally-associating-the-image-and-its-adjacent-long-description-html5)

HTML5 `<figure>` 요소는 이미지와 긴 설명을 모두 둘러싸는 데 사용할 수 있다.
긴 설명(제목, 텍스트 및 표로 표시됨)은 `<figcaption>` 요소로 감싼다.
`<figure>` 요소의 의미를 전달하지 않는 웹 브라우저에서는 포함된 `<figure>` 요소에 `role="group"`을 사용하여 이미지와 명시적으로 연결된다.

코드

```html
<figure role="group">
  <img
    src="chart.png"
    alt="Bar chart showing monthly and total visitors for the first quarter 2014 for sites 1 to 3, described in detail below."
  />
  <figcaption>
    <h2>Overview</h2>
    <p>The chart shows the website hits for the first quarter of 2014 …</p>
    <h2>Values</h2>
    <table>
      <caption>
        Example.com Site visitors Jan to March 2014
      </caption>
      <tr>
        …
      </tr>
    </table>
  </figcaption>
</figure>
```

#### [방법 4: `longdesc`를 통해 긴 설명에 대한 링크 제공](https://www.w3.org/WAI/tutorials/images/complex/#approach-4-providing-a-link-to-the-long-description-via-longdesc)

`longdesc` 속성에는 이미지에 대한 긴 설명을 제공하는 별도의 웹 페이지의 URI 또는 긴 설명을 제공하는 동일한 페이지의 요소를 참조하는 부분 식별자가 포함될 수 있다.

긴 설명이 포함된 다른 웹 페이지를 참조하는 URI가 `longdesc` 속성에 포함된
경우 [방법 1(이미지 옆에 긴 설명으로 가는 텍스트 링크)](https://www.w3.org/WAI/tutorials/images/complex/#approach-1-a-text-link-to-the-long-description-adjacent-to-the-image)
도 적용하는 것이 좋다.
이 방법은 `longdesc` 속성을 완전히 지원하지 않는 웹 브라우저 및 보조 기술을 위한 해결책이다.

코드

```html
<img
  src="chart.png"
  alt="Bar chart showing monthly and total visitors for the first quarter 2014 for sites 1 to 3"
  longdesc="2014-first-qtr.html"
/>
<a href="2014-first-qtr.html">Long Description</a>
```

`longdesc` 속성에 부분 식별자(# 뒤에 같은 웹 페이지에 있는 요소의 `id`, 해시 링크)가 포함된 경우 긴 설명을 제공하는 같은 웹 페이지의 요소를 참조한다.
웹 브라우저 및 보조 기술의 지원 여부는 다를 수
있지만 [두 번째 예제의 방법 1](https://www.w3.org/WAI/tutorials/images/complex/#example-2-description-containing-textual-information)
과 유사한 사례를 다룬다.
긴 설명이 이미지와 가까운 곳에 있는 경우 추가
링크([방법 1](https://www.w3.org/WAI/tutorials/images/complex/#approach-1-a-text-link-to-the-long-description-adjacent-to-the-image))
가 필요하지 않다.

### [예제 2: Description containing textual information](https://www.w3.org/WAI/tutorials/images/complex/#example-2-description-containing-textual-information)

WAI-ARIA `aria-describedby`
속성은 [`longdesc` 접근 방식](https://www.w3.org/WAI/tutorials/images/complex/#approach-4-providing-a-link-to-the-long-description-via-longdesc)
과 유사한 방식으로 동일한 웹 페이지의 어느 곳에서나 제공되는 이미지의 설명과 연결하는 데 사용할 수 있다.
속성 값은 긴 설명을 제공하는 요소의 `id`이다.

중요: `aria-describedby`에서 참조하는 요소는 하나의 연속된 텍스트 단락으로 취급된다.
스크린 리더 및 기타 보조 기술은 제목 및 표와 같은 구조적 정보에 접근할 수 없다.
이들은 구조적 관계를 표시하지 않고 해당 탐색 메커니즘 없이 포함된 모든 요소의 텍스트를 읽거나 제공한다.
따라서 이 방법은 이전 예제에서와 같이 구조적 정보가 필요 없이 텍스트만으로 구성된 긴 설명에만 작동한다.
이 예제에서는 웹 페이지에 있는 텍스트 단락을 사용하여 공작의 머리를 설명한다.

코드

```html
<img src="peacock.jpg" alt="Male peacock head" aria-describedby="description" />
[…]
<p id="description">
  The male is metallic blue on the crown, the feathers of the head being short
  and curled. The fan-shaped crest on the head is made of feathers with bare
  black shafts and tipped with blush-green webbing. A white stripe above the eye
  and a crescent shaped white patch below the eye are formed by bare white skin.
  The sides of the head have iridescent greenish blue feathers. The back has
  scaly bronze-green feathers with black and copper markings.
</p>
```

## [이미지 그룹](https://www.w3.org/WAI/tutorials/images/groups/)

때로는 여러 개의 이미지를 그룹으로 함께 사용하여 하나의 정보를 나타내기도 한다.
예를 들어 별표 아이콘 모음은 함께 등급을 나타낸다.
이 경우 이미지 중 하나만 전체 컬렉션을 설명하는 대체 텍스트가 필요하고 다른 이미지는 보조 기술에서 무시되도록 빈 `alt` 속성을 가진다.

다른 경우에는 이미지 그룹이 관련 이미지의 컬렉션을 나타낼 수 있다.
예를 들어, 주제와 관련된 예술 작품의 이미지 모음을 표시하는 경우가 있다.
이 경우 각 이미지에는 그룹 내 관계뿐만 아니라 개별적으로 이미지를 설명하는 대체 텍스트가 필요하다.

### [예제 1: 하나의 정보를 전달하는 여러 개의 이미지](https://www.w3.org/WAI/tutorials/images/groups/#example-1-multiple-images-conveying-a-single-piece-of-information)

다섯 개의 이미지가 결합된 이 그룹은 제품 등급을 표시한다.
5개의 이미지(채워진 별 3개, 반이 채워진 별 1개, 비어 있는 별 1개)가 전체 평점을 나타낸다.
첫 번째 이미지의 대체 텍스트는 "평점: 별 5개 중 3.5점". 다른 모든 이미지에는 빈 `alt` 속성(`alt=""`)이 있다.

코드

```html
Rating:
<img src="star-full.jpg" alt="3.5 out of 5 stars" />
<img src="star-full.jpg" alt="" />
<img src="star-full.jpg" alt="" />
<img src="star-half.jpg" alt="" />
<img src="star-empty.jpg" alt="" />
```

### [예제 2: 이미지 컬렉션](https://www.w3.org/WAI/tutorials/images/groups/#example-2-a-collection-of-images)

아래 예제에서는 HTML5 `<figure>` 및 `<figcaption>` 요소를 사용하여 컬렉션의 각 이미지에 캡션을 제공한다.
`<figure>` 요소는 중첩할 수 있으며, 이 예제에서는 전체 이미지 컬렉션에 대한 캡션을 제공하는 데 사용된다.
WAI-ARIA 속성 `role="group"`은 보조 기술에 이 그룹을 나타내는 데 사용되며, `aria-labelledby`는 `figcaption` 요소가 개별 그룹의 레이블로 사용되도록 한다.

참고: 웹 브라우저 및 보조 기술 지원은 이 특정 WAI-ARIA 속성 및 값에 따라 다르다.

코드

```html
<figure role="group" aria-labelledby="fig1">
  <figcaption id="fig1">
    The castle through the ages: 1423, 1756, and 1936 respectively.
  </figcaption>

  <figure role="group" aria-labelledby="fig11">
    <img
      src="castle-etching.jpg"
      alt="The castle has one tower, and a tall wall around it."
    />
    <figcaption id="fig11">Charcoal on wood. Anonymous, circa 1423.</figcaption>
  </figure>

  <figure role="group" aria-labelledby="fig12">
    <img
      src="castle-painting.jpg"
      alt="The castle now has two towers and two walls."
    />
    <figcaption id="fig12">
      Oil-based paint on canvas. Eloisa Faulkner, 1756.
    </figcaption>
  </figure>

  <figure role="group" aria-labelledby="fig13">
    <img
      src="castle-fluro.jpg"
      alt="The castle lies in ruins, the original tower all that remains in one piece."
    />
    <figcaption id="fig13">
      Film photograph. <span lang="fr">Séraphin Médéric Mieusement</span>, 1936.
    </figcaption>
  </figure>
</figure>
```

## [이미지 맵](https://www.w3.org/WAI/tutorials/images/imagemap/)

클라이언트 측 이미지 맵은 사용자 상호작용을 허용하는 `<area>` 요소(핫스팟)로 정의된 선택 가능한 영역으로 나뉜 이미지이다.
일반적으로 선택 가능한 영역은 다른 페이지로 연결되는 링크이다.
이미지 맵에서, `<img>` 요소 자체(정보 제공 컨텍스트를 전달)와 각 `<area>` 요소(링크 대상 또는 링크를 따라갈 경우 시작될 작업을 전달) 모두에 대체 텍스트가 필요하다.

### [예제 1: 개별 페이지로 연결되는 링크가 있는 조직도](https://www.w3.org/WAI/tutorials/images/imagemap/#example-1-an-organizational-chart-with-links-to-individual-pages)

아래 조직도는 각 이사의 홈페이지로 연결되는 링크를 제공하는 데 사용된다.
이미지의 대체 텍스트는 "이사회 및 관련 직원:"이다.
링크된 각 `<area>`에는 개인을 식별할 수 있는 대체 텍스트가 있다(예: "Davy Jones: 회장").
개인에 대한 대체 텍스트에는 그래프에서 그들의 관계도 명시한다.

코드

```html
<img
  src="orgchart.png"
  alt="Board of directors and related staff: "
  usemap="#Map"
/>
<map id="Map" name="Map">
  <area
    shape="rect"
    coords="176,14,323,58"
    href="[…]"
    alt="Davy Jones: Chairman"
  />
  […]
  <area
    shape="rect"
    coords="6,138,155,182"
    href="[…]"
    alt="Harry H Brown: Marketing Director (reports to chairman)"
  />
  […]
</map>
```

[a11y.md](..%2F..%2F..%2FDownloads%2Fa11y.md)
[이미지 맵 예제 전체 코드](https://www.w3.org/WAI/tutorials/images/examples/imagemap/)

이미지 맵에 대한 브라우저 구현은 작성 시점에 따라
다르다([HTML 버그 내용](https://lists.w3.org/Archives/Public/public-html-bugzilla/2015Jan/0020.html) 참고).
다양한 구현을 수용하려면 아래 사항에 유의해야 한다.

- 모든 이미지 맵은 한 번만 사용해야 한다. 즉, 동일한 맵이 포함된 여러 이미지를 사용하려면 맵을 복제하고 다른 `id`를 사용해야 한다.
- `<map>` 요소를 이미지의 직접 형제 요소로 배치해야 한다.

> 참고
>
> 영역의 좌표가 이미지와 동일한 비율로 조정되지 않은 경우 일부 모바일 기기에서 이미지 맵이 제대로 작동하지 않을 수 있다.
> 이를 보완하려면 같은 페이지에 중복으로 텍스트 링크를 제공해야 한다.

## [`alt` 결정 트리](https://www.w3.org/WAI/tutorials/images/decision-tree/)

이 결정 트리는 다양한 상황에서 `<img>` 요소의 `alt` 속성을 사용하는 방법을 설명한다.
일부 유형의 이미지에는 장식용으로 CSS 배경 이미지를 사용하거나 텍스트 이미지 대신 웹 글꼴을 사용하는 것과 같은 대체 방법이 있다.

### 이미지에 텍스트가 포함되어 있는가?

**아니오**: 다음으로.

**예**:

- **... 그리고 진짜 텍스트가 근처에 있다.**

  빈 `alt` 속성을 사용한다. [장식 이미지](https://www.w3.org/WAI/tutorials/images/decorative/) 참고.

- **... 그리고 텍스트가 시각 효과 용도로만 표시된다.**

  빈 `alt` 속성을 사용한다. [장식 이미지](https://www.w3.org/WAI/tutorials/images/decorative/) 참고.

- **... 그리고 텍스트에 특정 기능이 있다(예: 아이콘).**

  이미지의 기능을 알리는 용도로 `alt` 속성을 사용한다. [기능적 이미지](https://www.w3.org/WAI/tutorials/images/functional/) 참고.

- **... 그리고 그 외에 이미지 내의 텍스트가 없다.**

  이미지의 텍스트를 포함하는 `alt` 속성을 사용한다. [텍스트 이미지](https://www.w3.org/WAI/tutorials/images/textual/) 참고.

### 이미지가 링크나 버튼에 사용되는가? 그리고 이미지가 없는 경우 링크나 버튼이 어떤 역할인지를 이해하기가 어렵거나 불가능한가?

**아니오**: 다음으로.

**예**:
링크의 대상 또는 취해질 행동을 전달하는 용도로 `alt` 속성을 사용한다. [기능적 이미지](https://www.w3.org/WAI/tutorials/images/functional/) 참고.

### 이미지가 현재 페이지나 컨텍스트에 의미를 부여하는거?

**아니오**: 다음으로.

**예**:

- **... 그리고 이미지가 간단한 그래픽이나 사진이다.**

  이미지의 의미를 전달하는 간단한 설명을 `alt` 속성에 사용한다. [정보 제공 이미지](https://www.w3.org/WAI/tutorials/images/informative/) 참고.

- **... 그리고 이미지가 그래프이거나 복잡한 정보를 담는다.**

  페이지의 다른 곳에 이미지가 포함하는 정보를 추가한다. [복잡한 이미지](https://www.w3.org/WAI/tutorials/images/complex/) 참고.

- **... 그리고 근처의 진짜 텍스트와 중복되는 내용을 보여준다.**

  빈 `alt` 속성을 사용한다. [기능적 이미지](https://www.w3.org/WAI/tutorials/images/functional/) 참고.

### 이미지가 순전히 장식이거나 사용자를 위한 것이 아닌가?

**아니오**: 다음으로.

**예**:
빈 `alt` 속성을 사용한다. [장식 이미지](https://www.w3.org/WAI/tutorials/images/decorative/) 참고.

### 이미지를 사용하는 방식이 위에 없거나 어떤 `alt` 텍스트를 제공할지 명확하지 않은가?

이 결정 트리는 모든 경우를 대비하지 않는다. 대체 텍스트를 제공하는 자세한 내용은 [이미지 튜토리얼](https://www.w3.org/WAI/tutorials/images/)에 있다.

## [팁과 요령](https://www.w3.org/WAI/tutorials/images/tips/)

- **적절한 대체 텍스트 선택하기**

  웹 페이지를 이해해야 하는 사람에게 전화로 웹 페이지를 큰 소리로 읽어준다고 상상해 보자.
  이렇게 하면 이미지에 어떤 정보나 기능이 있는지 판단하는 데 도움이 된다.
  정보가 없어 보이고 링크나 버튼이 아닌 이미지는 장식으로 처리하는 것이 안전할 것이다.

- **대체 텍스트에 들어갈 정보에 우선순위를 정한다.**

  가장 중요한 정보를 맨 앞에 배치하는 것을 목표로 한다.

- **대체 텍스트의 길이**

  `alt` 텍스트는 이미지의 용도를 최대한 간결하게 설명해야 한다.
  짧은 구절이나 문장 이상의 설명이 필요한 경우 복잡한 이미지에서 설명한 긴 설명 방법 중 하나를 사용하는 것이 좋다.

- **반응형 디자인**

  텍스트 레이블이 있는 아이콘은 작은 화면에서 볼 때 텍스트 레이블이 아래로 내려가는 경우가 있다.
  아이콘이 해당 크기에서 읽을 수 있고, 텍스트 없이도 이해할 수 있으며, 텍스트 설명이 있는지 확인해야 한다.

- **`alt` 속성 내 구두점**

  - 모든 텍스트의 경우 텍스트 대체 속성에 구두점을 사용하면 정보를 더 쉽게 이해할 수 있다. 특히 이미지와 인접한 텍스트 사이에 공백 문자가 없는 경우 `alt` 텍스트에 공백 문자를 추가하여 스크린 리더가
    읽을 때 단어가 함께 이어지는 것을 방지해야 한다.

  - 장식 이미지를 숨기기 위해 비어 있는 대체 텍스트(`alt=""``)를 사용하는 경우 따옴표 사이에 공백 문자가 없는지 확인해야 한다.
    공백 문자가 있는 경우 보조 기술에서 이미지가 효과적으로 숨겨지지 않을 수 있다. 예를 들어 일부 스크린 리더는 따옴표 사이에 공백 문자가 있는 경우에도 이미지가 있음을 알린다.

- **대체 텍스트의 불필요한 정보**

  일반적으로 대체 텍스트에 '이미지', '아이콘' 또는 '그림'과 같은 단어를 포함할 필요가 없다. 볼 수 있는 사람들은 이미 이 사실을 알고 있으며 스크린 리더는 이미지가 있음을 알려준다. 일부 상황에서는 그림,
  사진, 일러스트레이션 등을 구분하는 것이 중요할 수 있지만 이러한 용어를 더 일반적으로 사용하는 것을 피하는 것이 가장 좋다.

- **SVG 그래픽**

  - SVG 그래픽은 다른 이미지 형식(PNG, JPEG, GIF)과 마찬가지로 `<img>` 요소의 `src` 속성에서 참조할 수 있다. 이 경우 이 튜토리얼의 예제는 SVG와도 사용할 수 있다.
  - SVG 이미지는 HTML과 같은 태그로 구성되므로 HTML5에서도 코드를 직접 사용할 수 있다. 이 경우 SVG 이미지 내 `<title>` 요소에 대체 텍스트를 입력할 수 있다. 접근성을 더 잘 지원하기
    위해 이 제목은 아래 예제처럼 `<svg>` 요소의 `aria-labelledby` 속성에서 참조해야 한다.

    ```html
    <svg aria-labelledby="svgtitle1">
      <title id="svgtitle1">Settings</title>
      [other svg code]
    </svg>
    ```

- **로고**

  텍스트가 포함된 로고 이미지는 일부 접근성 요건에서 면제된다. 예를 들어 최소 색상 대비 요구 사항이 없다.

### 기타 W3C 리소스

- "장애인이 웹을 사용하는 방법"
  에서 [텍스트가 아닌 콘텐츠에 대체 텍스트를 제공](https://www.w3.org/WAI/fundamentals/accessibility-principles/#alternatives)에 대한 배경 정보
- 본인 사이트에서 이미지의 접근성을 테스트해보자. - [이미지의 대체 텍스트 빠르게 확인하기](https://www.w3.org/WAI/test-evaluate/preliminary/#images)
- 대체 텍스트 선택하는 좋은 사례와 나쁜 사례의 예제는 [전후 데모(Before and After Demonstration, BAD)](https://www.w3.org/WAI/demos/bad/)에서 확인할 수
  있다.
