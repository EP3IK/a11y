# [페이지 구조 튜토리얼](https://www.w3.org/WAI/tutorials/page-structure/)

## [페이지 구조, 왜 중요할까?](https://www.w3.org/WAI/tutorials/page-structure/#why-is-this-important)

- **인지 및 학습 장애가 있는 사용자**가 페이지에서 콘텐츠를 더 쉽게 찾고 우선순위를 정할 수 있다.
- **화면 리더를 사용하는 사용자**가 주요 콘텐츠로 바로 건너뛰고 자신에게 중요한 섹션으로 이동할 수 있다.
- **키보드 사용자**가 페이지와 해당 섹션을 더 효율적으로 탐색할 수 있다.
  - 아니면 사용자는 탭 키를 여러 번 눌러서 각 섹션의 모든 링크를 탐색해야 한다.
- 웹 페이지의 **주요 콘텐츠만 표시하는 소프트웨어를 사용하는 사용자**가, 예를 들어 인지 장애가 있는 사용자의 경우, 페이지 구조가 올바르게 마크업되어 있으면 더 나은 결과를 얻을 수 있다.
- 저시력 장애인을 비롯한 **시각 장애인**이 페이지와 콘텐츠에 방향을 알려주는 단서를 얻는다.
- **모바일 웹 사용자**가 올바르게 마크업된 페이지에서만 주요 콘텐츠가 표시되는 '리더' 또는 '읽기' 모드에 접근할 수 있다.
- **특정 브라우저 플러그인을 사용하는 사용자**가 `landmark` 역할을 사용하여 페이지의 특정 섹션으로 이동할 수 있다.
- 장애인이 경험하는 것 외의 다른 장점
  - 검색 엔진은 페이지 구조 데이터를 사용해서 페이지 콘텐츠를 더 잘 색인할 수 있다.

## [페이지 영역](https://www.w3.org/WAI/tutorials/page-structure/regions/)

- 웹 페이지와 애플리케이션의 다양한 영역을 마크업해서 이를 웹 브라우저와 보조 기술에서 식별한다.

### [페이지 헤더](https://www.w3.org/WAI/tutorials/page-structure/regions/#page-header)

- 대부분의 웹사이트에는 웹사이트 로고, 검색 기능, 탐색 옵션 등 사이트 전반의 정보를 포함하는 영역이 모든 페이지 상단에 있다.
- HTML5는 이러한 영역을 정의하는 데 사용할 수 있는 `<header>` 요소를 제공한다.
- 참고: `<header>` 요소가 `<article>`, `<section>` 요소 안에 사용되는 경우 해당 요소와 연결되지 않는다. WAI-ARIA `banner` 역할을 수행하지 않으며 보조 기술에서 특별한 동작을 하지 않는다.
- 코드 스니펫
  ```html
  <header>
    …
    <img src="/images/logo.png" alt="SpaceBear Inc.">
    …
  </header>
  ```

### [페이지 푸터](https://www.w3.org/WAI/tutorials/page-structure/regions/#page-footer)

- 페이지 헤더와 마찬가지로 대부분의 웹사이트에는 모든 페이지 하단에 저작권 정보, 개인정보처리방침 또는 고지 사항과 같은 사이트 전체 정보가 포함된 영역이 있다.
- HTML5는 이러한 영역을 정의하는 데 사용할 수 있는 `<footer>` 요소를 제공한다.
- 참고: `<footer>` 요소도 `<header>`와 같이 `<article>`, `<section>` 요소 안에 사용되는 경우 해당 요소와 연결되지 않는다. WAI-ARIA `contentinfo` 역할을 수행하지 않으며 보조 기술에서 특별한 동작을 하지 않는다.
- 코드 스니펫
  ```html
  <footer>
    …
    <p>&copy; 2014 SpaceBears Inc.</p>
    …
  </footer>
  ```

### [탐색](https://www.w3.org/WAI/tutorials/page-structure/regions/#navigation)

- HTML5 `<nav>` 요소로 탐색 메뉴를 식별할 수 있다.
- 웹 페이지에는 여러 개의 탐색 메뉴가 있을 수 있다.
- 각 탐색 메뉴를 식별하려면 [레이블](https://www.w3.org/WAI/tutorials/page-structure/labels/)을 사용해야 한다.
- 코드 스니펫
  ```html
  <nav aria-label="Main">
    …
  </nav>
  …
  <nav aria-labelledby="regionheading">
    <h2 id="regionheading">On this page</h2>
    …
  </nav>
  ```
- 메뉴를 만드는 더 자세한 방법은 [메뉴 튜토리얼](https://www.w3.org/WAI/tutorials/menus/)을 참고.

### [메인 콘텐츠](https://www.w3.org/WAI/tutorials/page-structure/regions/#main-content)

- HTML5 `<main>` 요소로 웹 페이지 또는 애플리케이션의 주요 콘텐츠 영역을 식별한다.
- 코드 스니펫
  ```html
  <main>
    <h1>Stellar launch weekend for the SpaceBear 7!</h1>
    …
  </main>
  ```

### [메인 콘텐츠](https://www.w3.org/WAI/tutorials/page-structure/regions/#complementary-content)

- HTML5 `<aside>` 요소로 주요 콘텐츠를 지원하면서도 그 자체로 별개의 의미 있는 섹션인 영역을 식별한다(예: 주요 콘텐츠를 설명하거나 주석을 단 사이드 노트).
- 코드 스니펫
  ```html
  <aside>
    <h3>Related Articles</h3>
    …
  </aside>
  ```
  
### [반응형 디자인](https://www.w3.org/WAI/tutorials/page-structure/regions/#responsive-design)

- 작은 화면에서는 구성 요소를 접거나 아예 안 보이게 할 수 있지만 보이는 구성 요소는 특정 보기(크기 및 방향 설정)에 대해 동일한 순서로 표시되어야 한다.
- WCAG 요구 사항이 아니지만 가능하면 페이지 구조는 다양한 화면 크기와 방향에 걸쳐 일정해야 한다.

### [WAI-ARIA를 사용한 HTML5의 페이지 영역](https://www.w3.org/WAI/tutorials/page-structure/regions/#accessupport)

- 현재 대부분의 웹 브라우저는 위의 HTML5 요소를 지원하고 접근성 API로 보조 기술에 정보를 전달한다.
- 그러나 WAI-ARIA를 지원하면서 아직 HTML5를 지원하지 않는 웹 브라우저 및 보조 기술과의 호환성을 극대화하려면 현재는 HTML5 요소와 해당하는 WAI-ARIA 역할을 모두 사용하는 것이 좋다.
- HTML5 예시
  ```html
  <header role="banner">…</header>
  <main role="main">…</main>
  <nav role="navigation">…</nav>
  <footer role="contentinfo">…</footer>
  ```

### [WAI-ARIA를 사용한 HTML4의 페이지 영역](https://www.w3.org/WAI/tutorials/page-structure/regions/#accessupport-html4)

- HTML5를 사용할 수 없거나 접근성을 개선하기 위해 HTML4 페이지를 개조하는 경우, HTML5에 대응하는 기능을 하는 `div` 요소에 WAI-ARIA 코드를 추가한다.
- HTML4 예시
  ```html
  <div class="header" role="banner">…</div>
  <div id="main" role="main">…</div>
  <div id="nav" role="navigation">…</div>
  <div id="footer" role="contentinfo">…</div>
  ```

## [영역에 레이블 지정하기](https://www.w3.org/WAI/tutorials/page-structure/labels/)

- 같은 페이지에서 `<nav>` 요소를 사용하는 '주 탐색' 메뉴와 '보조 탐색' 메뉴와 같이 같은 유형의 두 페이지 영역을 구분하는 레이블을 제공한다.
- 레이블은 페이지 영역의 기본 식별을 변경하는 데도 사용할 수 있다(예: `<aside>` 영역을 '광고'로 식별).
- `<main>`과 같이 고유한 영역은 추가 레이블이 불필요하다.

### [`aria-labelledby`](https://www.w3.org/WAI/tutorials/page-structure/labels/#using-aria-labelledby)

* `aria-labelledby`에 ID를 사용하여 기존 요소를 가리킨다.
* 이때 영역의 레이블은 참조하는 요소의 콘텐츠이다.
* 레이블은 짧고 설명형이어야 한다.
* 영역에 제목이 있는 경우 제목을 레이블로 사용하는 것이 좋다.
  ```html
  <nav aria-labelledby="regionheading">
    <h2 id="regionheading">On this Page</h2>
      …
  </nav>
  ```

### [`aria-label`](https://www.w3.org/WAI/tutorials/page-structure/labels/#using-aria-label)

* WAI-ARIA `aria-label` 속성으로 영역에 레이블을 지정한다.
* 레이블이 페이지에 시각적으로 표시되지 않아야 하는 경우 이 방법을 고려할 수 있다.
  ```html
  <nav aria-label="Main">
    …
  </nav>
  ```
  
## [제목](https://www.w3.org/WAI/tutorials/page-structure/headings/)

- 제목은 페이지에 있는 콘텐츠가 어떻게 구성되었는지를 보여준다.
- 웹 브라우저, 플러그인 및 보조 기술은 이를 사용하여 페이지 내 탐색 기능을 제공할 수 있다.

### [제목 순위](https://www.w3.org/WAI/tutorials/page-structure/headings/#heading-ranks)

* 순위(레벨)에 따라 제목을 중첩한다.
* 가장 중요한 제목은 1순위(`<h1>`), 가장 중요하지 않은 제목은 6순위(`<h6>`)를 가진다.
* 순위가 같거나 높은 제목은 새 섹션을 시작하고 순위가 낮은 제목은 더 높은 순위의 섹션에 속하는 새 하위 섹션을 시작한다.
* 제목 순서를 건너뛰는 것은 혼란을 줄 수 있으므로 가급적 피해야 한다(예: :x:`<h2>` 바로 뒤에 `<h4>`).
* 하위 섹션을 닫을 때는 순위를 건너뛰어도 문제되지 않는다(예: 새 섹션을 시작하는 `<h2>`가 이전 섹션을 닫을 때 `<h4>` 뒤에 옴).

#### [고정된 페이지 섹션 예외](https://www.w3.org/WAI/tutorials/page-structure/headings/#exception-for-fixed-page-sections)

- 사이드바 등 페이지의 고정된 섹션에서는 콘텐츠 영역의 순위에 따라 제목 순위가 변경되지 않아야 한다.
- 이 경우 페이지 전반에 걸쳐 일관성을 유지하는 것이 더 중요하다.

### [텍스트 구절 정리](https://www.w3.org/WAI/tutorials/page-structure/headings/#organize-passages-of-text)

- 제목은 페이지의 텍스트 구절(예: 주요 콘텐츠)을 구성하는 데에만 사용한다.
- 예시

  ![One example (h1) heading (Space Teddy) with three h2 headings inside the content (Cotton Fur, Sapphire Eyes, Synthetic Felt Paws).](https://www.w3.org/WAI/content-images//tutorials/page-structure/page-structure-headings-intro@2x.png)

### [페이지 구성을 반영하는 제목](https://www.w3.org/WAI/tutorials/page-structure/headings/#headings-that-reflect-the-page-organization)

* 제목은 페이지 영역에 레이블을 지정하는 데 유용하다.
* [영역에 레이블 지정하기](#영역에-레이블-지정하기) 섹션에서 설명한 것처럼 `aria-labelledby`를 사용하여 제목을 해당 페이지 영역과 연결한다.
* 제목이 보이면 모든 사용자가 영역을 쉽게 식별할 수 있다.

### [예시1: 탐색 이전 메인 제목](https://www.w3.org/WAI/tutorials/page-structure/headings/#main-heading-before-navigation)

- 첫 번째 예시에서 1순위의 제목은 문서의 첫 번째 제목이다.
- 페이지를 구성하는 다른 모든 제목(탐색 메뉴, 사이드바, 푸터)은 한 순위가 낮고, 주 콘텐츠의 제목도 그렇다.

  ![One h1 heading with several h2s and h3 creating subsections. One subsection’s heading is ”(h3) Sapphire Eyes” which has a subsection “(h4) How they are made”. The next heading is an h2, indicating that the (h4) and (h3) subsections are both closed now.](https://www.w3.org/WAI/content-images//tutorials/page-structure/page-structure-headings@2x.png)

### [예시2: 탐색 이후 메인 제목](https://www.w3.org/WAI/tutorials/page-structure/headings/#main-heading-after-navigation)

- 두 번째 예시에서 주 제목은 사이트 이름이 아니라 콘텐츠 제목이고 이게 1순위이다.
- 다른 모든 구조 제목과 콘텐츠의 부제목은 2순위이다.

  ![The page starts with an (h2) Navigation Menu, followed by an (h2) Sidebar and an (h1) Space Teddy. The following headings are all (h2) subsections, including the footer which –](https://www.w3.org/WAI/content-images//tutorials/page-structure/page-structure-headings-2@2x.png)

## [콘텐츠 구조](https://www.w3.org/WAI/tutorials/page-structure/content/)

- 웹사이트 콘텐츠를 의미를 담아 마크업하여 웹사이트를 확장할 수 있도록 한다.
- 유효한 시맨틱은 재사용이 가능하고 보조 기술에 더 의미 있는 콘텐츠를 만든다.

### [아티클](https://www.w3.org/WAI/tutorials/page-structure/content/#articles)

- HTML5 `<article>` 요소는 웹 페이지의 완전한 또는 독립된 구성을 나타낸다.
- 예: 쇼핑 사이트의 상품, 뉴스 사이트의 뉴스 기사
- 코드 스니펫
  ```html
  <article>
    <h2>Space Bear Classic</h2>
    …
  </article>
  <article>
    <h2>Space Bear Extreme</h2>
    …
  </article>
  ```

### [섹션](https://www.w3.org/WAI/tutorials/page-structure/content/#sections)

- HTML5 `<section>` 요소는 웹 페이지 또는 글의 일반적인 영역을 표시한다.
- 콘텐츠를 주제별로 묶는 데 사용한다.
- 코드 스니펫
  ```html
  <section>
    <h2>Chapter 2</h2>
    …
  </section>
  ```

### [단락](https://www.w3.org/WAI/tutorials/page-structure/content/#paragraphs)

* 단락 요소(`<p>`)로 텍스트 단락을 표시할 수 있다.
* 단락의 스타일을 일정하게 맞추면 텍스트 가독성이 높아진다.
* 또한 사용자가 보기를 사용자화할 때 더 많은 제어 기능을 제공한다.

### [목록](https://www.w3.org/WAI/tutorials/page-structure/content/#lists)

- 정보의 성격에 따라 다양한 유형의 목록을 사용하여 정보를 묶어서 사용자에게 방향을 제시한다.
  * 정렬되지 않은 목록은 항목의 순서가 관련이 없는 경우에 사용한다. 정렬되지 않은 목록의 항목은 불릿으로 표시된다.
  * 정렬된 목록은 순서가 있는 정보에 사용되며 브라우저에서 자동으로 번호를 매긴다.
  * 설명 목록은 프로그램적으로 연결된 관련 용어 및 설명의 그룹이다.
- 개별 목록 항목에는 단락, 제목, 폼 요소, 다른(중첩된) 목록 등 다양한 HTML 요소를 포함할 수 있다.

#### [정렬되지 않은 목록](https://www.w3.org/WAI/tutorials/page-structure/content/#unordered-list)

* 하나의 `<ul>` 요소와 여러 개의 목록 항목(`<li>`)으로 이루어진다.
* 예시
  * Corn
  * Tomatoes
  * Beans
  * Onions
  * Garlic
* 코드 스니펫
  ```html
  <ul>
    <li>Corn</li>
    <li>Tomatoes</li>
    <li>Beans</li>
    <li>Onions</li>
    <li>Garlic</li>
  </ul>
  ```

#### [정렬된 목록](https://www.w3.org/WAI/tutorials/page-structure/content/#ordered-list)

* 하나의 `<ol>` 요소와 여러 개의 목록 항목(`<li>`)으로 이루어진다.
* 예시
  1. Cook beans for 45 minutes.
  2. Cut vegetables in small cubes.
  3. Sauté onions and garlic.
  4. Deglaze using the tomatoes.
  5. Add corn and beans.
* 코드 스니펫
  ```html
  <ol>
    <li>Cook beans for 45 minutes.</li>
    <li>Cut vegetables in small cubes.</li>
    <li>Sauté onions and garlic.</li>
    <li>Deglaze using the tomatoes.</li>
    <li>Add corn and beans.</li>
  </ol>
  ```

#### [중첩 목록](https://www.w3.org/WAI/tutorials/page-structure/content/#nested-lists)

* 모든 목록은 다른 목록에 중첩할 수 있다.
* 아래 예시에서, 준비하는 순서는 중요하지 않지만 준비 자체는 재료를 사용하기 전에 끝나야 한다.
* 정보는 여전히 이해하기 쉽고 보조 기술은 사용자에게 단계 개수를 쉽게 알릴 수 있습니다.
* 예시
  1. Prepare ingredients
     - Cook beans for 45 minutes.
     - Cut vegetables in small cubes.
  2. Sauté onions and garlic.
  3. Deglaze using the tomatoes.
  4. Add corn and beans.
* 코드 스니펫
  ```html
  <ol>
    <li>
      Prepare ingredients
      <ul>
        <li>Cook beans for 45 minutes.</li>
        <li>Cut vegetables in small cubes.</li>
      </ul>
    </li>
    <li>Sauté onions and garlic.</li>
    <li>Deglaze using the tomatoes.</li>
    <li>Add corn and beans.</li>
  </ol>
  ```

#### [설명 목록](https://www.w3.org/WAI/tutorials/page-structure/content/#description-lists)

* 설명 목록은 하나 이상의 용어 및 설명 그룹으로 이루어진다.
* 각 그룹은 하나 이상의 용어(`<dt>` 요소의 내용)를 하나 이상의 설명(`<dd>` 요소의 내용)과 연결합니다.
* 그룹화는 목록의 첫 번째 항목에서 또는 `<dt>` 요소가 `<dd>` 요소 뒤에 올 때 시작한다.

##### [예시1: 하나의 용어, 여러 개의 설명](https://www.w3.org/WAI/tutorials/page-structure/content/#one-term-multiple-descriptions)
* 예시
  <dl>
    <dt>Authors</dt>
    <dd>John</dd>
    <dd>Luke</dd>
    <dt>Editor</dt>
    <dd>Frank</dd>
  </dl>
* 코드 스니펫
  ```html
  <dl>
    <dt>Authors</dt>
    <dd>John</dd>
    <dd>Luke</dd>
    <dt>Editor</dt>
    <dd>Frank</dd>
  </dl>
  ```
##### [예시2: 여러 개의 용어, 하나의 설명](https://www.w3.org/WAI/tutorials/page-structure/content/#multiple-terms-one-description)
* 예시
  <dl>
    <dt lang="en-US"><dfn>color</dfn></dt>
    <dt lang="en-GB"><dfn>colour</dfn></dt>
    <dd>A sensation which (in humans) derives from the ability of the fine structure of the eye to distinguish three differently filtered analyses of a view.</dd>
  </dl>
* 코드 스니펫
  ```html
  <dl>
    <dt lang="en-US"><dfn>color</dfn></dt>
    <dt lang="en-GB"><dfn>colour</dfn></dt>
    <dd>A sensation which (in humans) derives from the ability of the fine structure of the eye to distinguish three differently filtered analyses of a view.</dd>
  </dl>
  ```
##### [예시3: 여러 개의 용어, 여러 개의 설명](https://www.w3.org/WAI/tutorials/page-structure/content/#multiple-terms-multiple-descriptions)
* 예시
  <dl>
    <dt>Authors</dt>
    <dt>Editors</dt>
    <dd>John</dd>
    <dd>Luke</dd>
  </dl>
* 코드 스니펫
  ```html
  <dl>
    <dt>Authors</dt>
    <dt>Editors</dt>
    <dd>John</dd>
    <dd>Luke</dd>
  </dl>
  ```
  
### [인용](https://www.w3.org/WAI/tutorials/page-structure/content/#quotes)

* 인용을 식별하면 콘텐츠의 출처가 다른 작성자임을 명시할 수 있다.
* 인용은 인라인으로 표시하거나 텍스트 블록으로 표시할 수 있다.
* 보조 기술을 통해 인용문의 시작과 끝을 사용자에게 전달하여 오해를 피할 수 있다.

#### [예시1: 블록 인용](https://www.w3.org/WAI/tutorials/page-structure/content/#blockquote)

* 더 길고 복잡한 인용에는 `<blockquote>` 요소를 사용한다.
* 단락, 제목 및 다른 텍스트 구조 요소를 포함할 수 있고 이러한 요소는 인용된 문서의 구조를 반영해야 한다.
* `<cite>` 요소는 인용문의 출처를 가리키는 데 사용한다.
* 예시
  <p>The following is an excerpt from the <cite>The Story of my Life</cite> by Helen Keller</p>
  <blockquote>
    <p>Even in the days before my teacher came, I used to feel along the square stiff boxwood hedges, and, guided by the sense of smell, would find the first violets and lilies. There, too, after a fit of temper, I went to find comfort and to hide my hot face in the cool leaves and grass.</p>
  </blockquote>
* 코드 스니펫
  ```html
  <p>The following is an excerpt from the <cite>The Story of my Life</cite> by Helen Keller</p>
  <blockquote>
    <p>Even in the days before my teacher came, I used to feel along the square stiff boxwood hedges, and, guided by the sense of smell, would find the first violets and lilies. There, too, after a fit of temper, I went to find comfort and to hide my hot face in the cool leaves and grass.</p>
  </blockquote>
  ```

#### [예시2: 인라인 인용](https://www.w3.org/WAI/tutorials/page-structure/content/#inline-quote)

- 다른 문장에 포함되는 짧은 인용은 `<q>` 요소를 사용한다.
- 예시
  <p>Helen Keller said, <q>Self-pity is our worst enemy and if we yield to it, we can never do anything good in the world.</q></p>
- 코드 스니펫
  ```html
  <p>Helen Keller said, <q>Self-pity is our worst enemy and if we yield to it, we can never do anything good in the world.</q></p>
  ```
  
### [그림](https://www.w3.org/WAI/tutorials/page-structure/content/#figures)

* 그림은 페이지의 주 콘텐츠에서 설정된 추가 정보 블록이다.
  * 때로는 주요 텍스트에서 참조할 수 있다.
* 일반적으로 목록, 이미지, 표를 포함하지만 다른 콘텐츠도 포함할 수 있다.
* 예: 연례 보고서에서 제품의 판매량이 포함된 다이어그램을 참조할 수 있다.
* 각 그림은 `<figure>` 요소로 감싸고 중첩된 `<figcaption>` 요소를 사용하여 레이블을 지정한다.
* 코드 스니펫
  ```html
  <p>The sales volume of our SpaceBear product was steadily the first three quarters but had a huge success in quarter four with the introduction of SuperBear in time for the holiday season. See graphic G3 for details.</p>
  <figure role="group" aria-labelledby="fig-t3-capt">
    <figcaption id="fig-t3-capt">G3: SpaceBear sales volume</figcaption>
    <img src="…"
      alt="SpaceBear sales diagram, showing the huge success in Q4"
      longdesc="…">
    <a href="…">Long Description</a>
  </figure>
  ```

### [이미지 및 일러스트레이션](https://www.w3.org/WAI/tutorials/page-structure/content/#images-and-illustrations)

* 이미지와 일러스트레이션은 많은 사용자의 시각적 참여를 유도하는 데 유용하다.
* 또한 읽기 장애가 있는 사람들을 위해 텍스트를 명확하게 설명할 수도 있다.
* 이미지나 일러스트레이션을 사용하는 경우에는 적절한 대체 텍스트를 추가해야 한다.
* 대체 텍스트에 대한 가이드는 [이미지 튜토리얼](https://www.w3.org/WAI/tutorials/images/)을 참고.

### [테이블](https://www.w3.org/WAI/tutorials/page-structure/content/#tables)

* 데이터 테이블은 테이블 구조를 모두에게 전달할 수 있게 데이터를 표시하는 유용한 방법이다.
* 적절하게 테이블 레이아웃을 사용하면 사람들이 그리드를 보지 않고도 의미 있는 데이터 관계를 이해할 수 있다.
* 자세한 내용은 [테이블 튜토리얼](https://www.w3.org/WAI/tutorials/tables/)을 참고.

## [페이지 구조 코드 예시](https://www.w3.org/WAI/tutorials/page-structure/example/)

```html
…
<body>
  <header>
    <h1>Space Teddy Inc.</h1>
  </header>
  <nav aria-labelledby="mainnavheader">
    <h2 id="mainnavheader">Navigation Menu</h2>
    …
  </nav>
  <main>
    <article>
      <h2>An inside look at the new Space Teddy 6</h2>
      <nav aria-labelledby="tocheader">
        <h3 id="tocheader">Table of Contents</h3>
        …
      </nav>
      <p>…</p>
      <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
      <p>…</p>
      <ul>
        <li>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</li>
        <li>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</li>
        <li>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</li>
      </ul>
      <h3>Cotton Fur</h3>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      <p>…</p>
      <aside aria-labelledby="relatedheader">
        <h3 id="relatedheader">Related Articles</h3>
        <ul>
          <li><a href="#">Related Article Title 1</a></li>
          <li><a href="#">Related Article Title 2</a></li>
          <li><a href="#">Related Article Title 3</a></li>
        </ul>
      </aside>
    </article>
    <aside aria-labelledby="latestheader">
      <h3 id="latestheader">Latest Articles</h3>
      <ul>
        <li><a href="#">Latest Article Title 1</a></li>
        <li><a href="#">Latest Article Title 2</a></li>
        <li><a href="#">Latest Article Title 3</a></li>
      </ul>
    </aside>
  </main>
  <footer>
    <p>© SpaceTeddy Inc.</p>
  </footer>
</body>
…
```