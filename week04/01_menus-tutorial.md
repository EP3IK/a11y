# [메뉴 튜토리얼](https://www.w3.org/WAI/tutorials/menus/)

## [메뉴, 왜 중요할까?](https://www.w3.org/WAI/tutorials/menus/#why-is-this-important)

- 다양한 방식으로 메뉴를 조작할 수 있게 마크업되거나 키보드 상호 운용성을 갖추면 **스크린 리더 및 키보드 사용자**에게 좋다.
- **소근육 운동에 어려움이 있는 사용자와 터치스크린 사용자**는 클릭하거나 탭하는 타겟의 크기가 더 커야 한다. 플라이아웃 메뉴에서는 마우스가 클릭 가능한 영역을 벗어난 후 하위 메뉴가 즉시 사라지지 않아야 한다.
- 현재 페이지를 보여주는 것과 같이 상태가 쉽게 잘 보이는 뚜렷한 메뉴는 **주의력이 부족하거나 단기 기억력이 약한 사용자**에게 좋다.

## [메뉴 구조](https://www.w3.org/WAI/tutorials/menus/structure/)

- 시멘틱 마크업은 메뉴의 구조를 사용자에게 전달한다.
- 메뉴의 코드를 의미론적으로 작성하면 작은 화면, 화면 확대 및 기타 보조 기술과 같은 다양한 상황에 쉽게 대응할 수 있다.

### [메뉴 표현법](https://www.w3.org/WAI/tutorials/menus/structure/#menu-representation)

- 일반적으로 목록을 사용해서 메뉴 구조를 전달한다.
- 이러한 구조 정보를 통해 보조 기술은 메뉴의 항목 개수를 알려주고 그에 맞는 탐색 기능을 제공한다.

#### [방법1: 정렬되지 않은 목록](https://www.w3.org/WAI/tutorials/menus/structure/#unordered-list)

- 메뉴 항목이 특정 순서가 아닌 경우 정렬되지 않은 목록(`<ul>`)을 사용한다.
- 웹사이트 탐색과 같은 대부분의 메뉴 유형이 이 범주에 속한다.
- 코드
  ```html
  <ul>
    <li><a href="…">Home</a></li>
    <li><a href="…">Shop</a></li>
    <li><a href="…">Space Bears</a></li>
    <li><a href="…">Mars Cars</a></li>
    <li><a href="…">Contact</a></li>
    …
  </ul>
  ```

#### [방법2: 정렬된 목록](https://www.w3.org/WAI/tutorials/menus/structure/#ordered-list)

- 메뉴 항목의 순서가 중요한 경우 정렬된 목록(`<ol>`)을 사용한다.
- 아래 예에서 메뉴 항목은 구성 매뉴얼의 단계를 나타낸다.
- 코드
  ```html
  <ol>
    <li><a href="…">Unpacking the Space Craft</a></li>
    <li><a href="…">Check Contents of Package</a></li>
    <li><a href="…">Build Chassis</a></li>
    <li><a href="…">Build Engine</a></li>
    <li><a href="…">Mount Engine to Chassis</a></li>
    …
  </ol>
  ```

### [메뉴를 식별하기](https://www.w3.org/WAI/tutorials/menus/structure/#identify-menus)

- 사용자가 메뉴에 직접 접근할 수 있게 메뉴를 식별하는 방법은 HTML5 `<nav>` 요소를 사용하는 것이 이상적이다.
- 메뉴를 마크업하는 다른 기법은 [페이지 영역](https://www.w3.org/WAI/tutorials/page-structure/regions/) 튜토리얼에 설명되어 있다.
- 코드
  ```html
  <nav>
    <ul>
      …
    </ul>
  </nav>
  ```

### [메뉴에 레이블 지정하기](https://www.w3.org/WAI/tutorials/menus/structure/#label-menus)

- 메뉴를 더 쉽게 찾고 이해할 수 있도록 메뉴에 레이블을 지정한다.
- 레이블은 사용자가 웹 페이지의 여러 메뉴를 구분할 수 있도록 짧지만 설명형이어야 한다.
- 제목, `aria-label` 또는 `aria-labelledby`를 사용하여 레이블을 제공한다.
- 이러한 기법은 [영역에 레이블 지정하기](https://www.w3.org/WAI/tutorials/page-structure/labels/) 튜토리얼에 설명되어 있다.
- 코드
  ```html
  <nav aria-labelledby="mainmenulabel">
    <h2 id="mainmenulabel" class="visuallyhidden">Main Menu</h2>
  </nav>
  ```

### [현재 항목을 나타내기](https://www.w3.org/WAI/tutorials/menus/structure/#indicate-the-current-item)

- 마크업을 사용하여 웹사이트의 현재 페이지와 같은 메뉴의 현재 항목을 표시하여 메뉴의 방향을 개선할 수 있다.

#### [방법1: 보이지 않는 텍스트를 사용](https://www.w3.org/WAI/tutorials/menus/structure/#using-invisible-text)

- 보이지 않는 레이블을 제공하면 스크린 리더 사용자에게 소리내어 읽히고 다른 보조 기술에서 사용자 지정 레이블 텍스트를 지원하는 현재 항목을 표시하는 데 사용된다.
- 앵커(`<a>`)를 제거해야 사용자가 현재 항목과 상호 작용할 수 없습니다. 이렇게 하면 잘못 이해하는 것을 피하고 현재 메뉴 항목이 활성화되어 있음을 강조할 수 있습니다.
- 아래 예에서 메뉴 항목에는 "Current Page:"라는 보이지 않는 텍스트가 있고 `<a>` 요소는 `current` 클래스가 있는 `<span>`으로 대체되었다.
- 코드
  ```html
  <li>
    <span class="current">
      <span class="visuallyhidden">Current Page: </span>
      Space Bears
    </span>
  </li>
  ```

#### [방법2: WAI-ARIA 사용](https://www.w3.org/WAI/tutorials/menus/structure/#using-wai-aria)

- `aria-current="page"` 속성을 사용하면 메뉴에서 현재 페이지를 표시할 수 있다.
- 이 기법은 HTML에서 앵커(`<a>`)를 없앨 수 없을 때 특히 유용하다.
- 아래 예제에서는 탐색의 링크가 페이지의 주요 콘텐츠로 연결된다.
- 코드
  ```html
  <li>
    <a href="#main" aria-current="page"> Space Bears </a>
  </li>
  ```

### [반응형 디자인](https://www.w3.org/WAI/tutorials/menus/structure/#responsive-design)

- 메뉴 구조는 화면 크기에 관계없이 일관되어야 한다.
- 일부 메뉴 항목은 하위 탐색 메뉴에서 접히거나 숨길 수 있지만 보이는 항목은 동일한 순서와 동일한 문구 및 목적지로 표시되어야 한다.

## [메뉴 스타일링](https://www.w3.org/WAI/tutorials/menus/styling/)

- 명확하고 일관된 스타일링은 사용자가 메뉴를 더 빨리 찾고 인식할 수 있게 한다.
- 이러한 스타일링에는 웹사이트 전반에 걸쳐서 페이지의 동작, 모양 및 상대적 위치의 일관성이 있다.

### [일반적인 고려 사항](https://www.w3.org/WAI/tutorials/menus/styling/#general-considerations)

- 메뉴에는 꾸미는 용도로 또는 기능을 전달할 용도로 아이콘 등의 이미지가 사용되는 경우가 있다.
- 이러한 이미지에는 [이미지 튜토리얼](https://www.w3.org/WAI/tutorials/images/)에 설명된 것과 같이 대체 텍스트가 필요하다.
- 명암 대비 요구사항도 메뉴와 항목에 적용할 수 있다.

#### [위치](https://www.w3.org/WAI/tutorials/menus/styling/#location)

- 웹사이트의 대상 고객이 기대하는 위치에 메뉴를 표시한다.
- 예를 들어 웹사이트의 기본 탐색 메뉴는 왼쪽에서 오른쪽으로 읽는 언어권 기준으로 보통 페이지 왼쪽에 세로로 배치되거나 상단에 가로로 배치한다.
- 애플리케이션 메뉴는 일반적으로 상단에 가로로 배치된다.

#### [식별](https://www.w3.org/WAI/tutorials/menus/styling/#identification)

- 메뉴와 항목을 식별할 수 있어야 한다.
- 이전 섹션에서 설명한 구조적 마크업 외에도 메뉴와 항목이 있다는 것을 시각적으로 전달하기 위해서는 색상 구성이 필요하다.
- 모든 사용자에게 메뉴 레이블을 잘 보이게 하려면 어떻게 해야 할까? [이 튜토리얼 페이지](https://www.w3.org/WAI/EO/Drafts/tutorials/navigation/styling/)를 예로 들면 "Menus Tutorial", "All Tutorials", "On this page"는 모든 사용자가 볼 수 있는 표시되는 제목으로 제공되는 메뉴 레이블이다.

#### [가독성](https://www.w3.org/WAI/tutorials/menus/styling/#readability)

- 모든 텍스트에 맞게 메뉴와 메뉴 항목의 크기를 적절히 조정해야 한다.
- 메뉴 크기는 또한 단어 길이가 더 긴 언어와 텍스트를 크게 보는 사람들을 위해서 다양한 텍스트 크기에 맞게 대응할 수 있어야 한다.
- 대문자 텍스트, 줄바꿈, 하이픈 처리는 산만하고 읽기 어려운 경우가 많기 때문에 가능하면 모두 피하는 것이 좋다.

#### [크기](https://www.w3.org/WAI/tutorials/menus/styling/#size)

- 모바일 기기의 작은 터치스크린과 손재주가 약한 사용자를 위해 패딩과 같이 충분한 여백을 제공해야 한다.
- 동시에 사용자가 텍스트 크기를 늘리거나 페이지를 확대할 때 메뉴가 다른 메뉴나 페이지의 다른 콘텐츠와 겹치지 않게 해야 한다.

### [메뉴 항목](https://www.w3.org/WAI/tutorials/menus/styling/#menu-items)

- 색상과 기타 스타일링 옵션을 사용하여 메뉴 항목과 해당 상태를 전달한다.
- 일부 사용자는 이러한 변경 사항을 인식하지 못할 수 있으므로 색상에만 의존하면 안 된다.
- 예를 들어 메뉴 항목이 선택되었을 때 색상을 변경하는 것 외에 메뉴 항목의 모양을 변경하거나 아이콘을 추가할 수 있다.

#### [기본 상태](https://www.w3.org/WAI/tutorials/menus/styling/#default-state)

- 고유한 스타일을 사용해서 메뉴 항목을 페이지에서 활성화할 수 있는 영역으로 시각적으로 표시한다.
- 하지만, 대문자나 작은 글씨로 된 단어와 같이 텍스트를 과하게 꾸미는 것은 텍스트를 읽기 어렵게 만들 수 있으므로 피해야 한다.

#### [호버, 포커스 상태](https://www.w3.org/WAI/tutorials/menus/styling/#hover-and-focus-states)

- 메뉴를 탐색할 때 호버링되거나 포커스된 메뉴 항목을 변경하면 사용자에게 시각적으로 안내할 수 있다.
- 아래 예제에서 호버, 포커스 상태는 반전된 색상 구성(흰 배경에 파란 글씨가 아닌 파란 배경에 흰 글씨)와 밑줄을 사용한다.
- 코드
  ```CSS
  nav a:hover,
  nav a:focus {
    color: #036;
    background-color: #fff;
    text-decoration: underline;
  }
  ```

#### [활성 상태](https://www.w3.org/WAI/tutorials/menus/styling/#active-state)

- 클릭, 탭 또는 키보드 선택을 통해 활성화된 메뉴 항목을 표시한다.
- 잘못된 메뉴 항목을 클릭한 경우와 같이 의도하지 않은 활성화를 사용자가 식별할 수 있다.
- 아래 예제에서 활성화된 항목은 진한 파란색 배경에 밑줄이 그어진다.
- 코드
  ```CSS
  nav [aria-current=page] {
    background-color: #bbb;
    color: #000;
    border-bottom: .25em solid #444;
  }
  ```

#### [현재 상태](https://www.w3.org/WAI/tutorials/menus/styling/#current-state)

- 이전 섹션에서 설명한 구조적 마크업과 더불어 현재 메뉴 항목을 시각적으로 표시한다.
- 아래 예제에서 현재 메뉴 항목에 뚜렷한 색상과 모양을 주기 위해 다른 색상 조합(회색에 검은색)과 하단 테두리를 추가한다.
- 코드
  ```CSS
  nav [aria-current=page] {
    background-color: #bbb;
    color: #000;
    border-bottom: .25em solid #444;
  }
  ```

#### [방문한 상태](https://www.w3.org/WAI/tutorials/menus/styling/#visited-state)

- 안내 단계와 같은 일부 메뉴 유형의 경우 사용자가 이미 방문한 적이 있는 메뉴 항목을 표시하는 것이 유용할 수 있다.
- 그러나 대부분의 메뉴는 방문한 상태에 따라 변경되지 않는다.

## [드롭다운 메뉴](https://www.w3.org/WAI/tutorials/menus/flyout/)

- 드롭다운 메뉴를 사용하면 웹사이트의 페이지 계층 구조에 대한 개요를 제공할 수 있다.
- 사용자가 정보의 위치를 안다면 여러 페이지를 로드하지 않아도 되게끔 한다.
- 애플리케이션 메뉴도 비슷하게 구현하지만, WAI-ARIA 마크업이 추가된다.
- 손떨림 등 손재주가 약한 사람은 드롭다운 메뉴를 조작하는 데 어려움을 겪을 수 있고 어떤 사람은 사용이 아예 불가능할 수 있다.
- 상위 메뉴 항목의 페이지에서 하위 메뉴 항목을 다시 보여주는 것과 같이 하위 메뉴 항목에 도달할 수 있는 다른 방법을 제공해야 한다.

### [하위 메뉴 표시](https://www.w3.org/WAI/tutorials/menus/flyout/#indicate-submenus)

- 시각적으로 그리고 마크업을 사용하여 하위 메뉴가 있는 탐색 메뉴 항목을 표시한다.
- 아래 예제에서는 하위 메뉴를 아이콘으로 시각적으로 표시한다.
- WAI-ARIA 마크업 `aria-expanded="false"`는 하위 메뉴 탐색이 현재 숨겨져 있거나 "접혀 있음"을 선언한다.
- 코드
  ```html
  <nav aria-label="Main">
    <ul>
      <li><a href="…">Home</a></li>
      <li><a href="…">Shop</a></li>
      <li class="has-submenu">
        <a href="…" aria-expanded="false"> Space Bears </a>
        <ul>
          <li><a href="…">Space Bear 6</a></li>
          <li><a href="…">Space Bear 6 Plus</a></li>
        </ul>
      </li>
      <li><a href="…">Mars Cars</a></li>
      <li><a href="…">Contact</a></li>
    </ul>
  </nav>
  ```

### [드롭다운 기능](https://www.w3.org/WAI/tutorials/menus/flyout/#fly-out-functionality)

- 드롭다운 기능은 마우스와 키보드 사용자를 따로 고려해서 CSS와 스크립트로 만든다.

#### [마우스 사용자](https://www.w3.org/WAI/tutorials/menus/flyout/#mouse-users)

- 아래 예제에서는 CSS 코드를 사용해서 상위 메뉴 항목에 마우스를 가져갔을 때 하위 메뉴를 보여주거나 숨긴다.
- 코드

  ```CSS
  nav > ul li       ul { display: none; }
  nav > ul li:hover ul { display: block;}
  ```

- 추가로 마우스가 해당 영역을 벗어날 때 하위 메뉴 항목이 바로 닫히는 것을 약간 지연하기 위해서 스크립트를 사용한다.
- 이 지연을 통해 정밀하게 마우스로 탐색하지 못할 때 메뉴를 더 쉽게 사용할 수 있다.
- 아래 예제에서는 타이머로 1초의 지연을 추가한다.
- 코드
  ```Javascript
  var menuItems = document.querySelectorAll('li.has-submenu');
  Array.prototype.forEach.call(menuItems, function(el, i){
    el.addEventListener("mouseover", function(event){
      this.className = "has-submenu open";
      clearTimeout(timer);
    });
    el.addEventListener("mouseout", function(event){
      timer = setTimeout(function(event){
        document.querySelector(".has-submenu.open").className = "has-submenu";
      }, 1000);
    });
  });
  ```

#### [키보드 사용자](https://www.w3.org/WAI/tutorials/menus/flyout/#keyboard-users)

- 메뉴를 탐색하려고 탭 키를 사용할 때 하위 메뉴가 열리면 안 되는데, 이러면 키보드 사용자가 다음 최상위 항목으로 이동하기 위해 모든 하위 메뉴 항목을 거쳐야 하기 때문이다.
- 대신 다음 접근 방식 중 하나를 고려할 수 있다.

##### [방법1: 상위 메뉴를 토글로 사용](https://www.w3.org/WAI/tutorials/menus/flyout/#use-parent-as-toggle)

- 상위 메뉴 항목이 하위 메뉴를 요약하기만 하고 웹 페이지 링크와 같은 기능을 수행할 필요가 없는 상황에서 이 접근 방식을 사용한다.
- 이 경우 사용자가 최상위 항목을 활성화하면 스크립트에 의해 하위 메뉴가 열리고 포커스가 하위 메뉴에서 벗어나면 하위 메뉴가 닫힌다.
- 참고
  - `href` 속성의 값은 무시하지만 자바스크립트가 로드되지 않을 때를 대비해서 기존 문서에 링크하고 싶을 수 있다.
- 아래 코드는 `has-submenu` 클래스가 있는 모든 최상위 항목을 순회하면서 상태에 따라 하위 메뉴를 열거나 닫는 클릭 이벤트를 추가한다.
- 또 하위 메뉴가 열려 있으면 `aria-expanded` 속성을 `true`로 설정하고 그렇지 않으면 `false`로 설정한다.
- 참고
  - 이름과 다르게 클릭 이벤트는 입력 방식에 관계없이(클릭이 아니어도) 링크가 활성화되면 즉시 발동한다.
- 코드
  ```Javascript
  var menuItems = document.querySelectorAll('li.has-submenu');
  Array.prototype.forEach.call(menuItems, function(el, i){
    el.querySelector('a').addEventListener("click",  function(event){
      if (this.parentNode.className == "has-submenu") {
        this.parentNode.className = "has-submenu open";
        this.setAttribute('aria-expanded', "true");
      } else {
        this.parentNode.className = "has-submenu";
        this.setAttribute('aria-expanded', "false");
      }
      event.preventDefault();
      return false;
    });
  });
  ```

##### [방법2: 버튼을 토글로 사용](https://www.w3.org/WAI/tutorials/menus/flyout/#use-button-as-toggle)

- 상위 메뉴 항목이 웹 페이지 링크와 같은 기능을 수행해야 하는 경우 상위 항목에 별도의 버튼을 추가하여 하위 메뉴를 열고 닫을 수 있다.
- 이 버튼은 하위 메뉴가 있음을 시각적으로 표시하는 역할도 할 수 있다.
- 아래 코드는 하위 메뉴가 있는 모든 최상위 메뉴 항목에 버튼을 추가한다.
- 버튼을 활성화하면 하위 메뉴를 보여주거나 숨긴다.
- 버튼의 보이지 않는 레이블은 하위 메뉴의 상태를 반영하여 "show submenu" 또는 "hide submenu"로 설정되어 있다.
- 참고
  - 가능하면 버튼의 레이블에 상위 메뉴 항목의 이름을 포함하는 것이 좋다(ex: "Space Bears 하위 메뉴 보기").
- 코드

  ```Javascript
  var menuItems = document.querySelectorAll('li.has-submenu');
  Array.prototype.forEach.call(menuItems, function(el, i){
    var activatingA = el.querySelector('a');
    var btn = '<button><span><span class="visuallyhidden">show submenu for “' + activatingA.text + '”</span></span></button>';
    activatingA.insertAdjacentHTML('afterend', btn);

    el.querySelector('button').addEventListener("click",  function(event){
      if (this.parentNode.className == "has-submenu") {
        this.parentNode.className = "has-submenu open";
        this.parentNode.querySelector('a').setAttribute('aria-expanded', "true");
        this.parentNode.querySelector('button').setAttribute('aria-expanded', "true");
      } else {
        this.parentNode.className = "has-submenu";
        this.parentNode.querySelector('a').setAttribute('aria-expanded', "false");
        this.parentNode.querySelector('button').setAttribute('aria-expanded', "false");
      }
      event.preventDefault();
    });
  });
  ```

## [애플리케이션 메뉴](https://www.w3.org/WAI/tutorials/menus/application-menus/)

- 웹 애플리케이션 메뉴는 탐색 메뉴와 동일한 기본 구조를 사용한다.
- 가로 메뉴 막대로 구성되며 드롭다운 기능을 사용하는 경우가 많다.
- 그러나 추가 마크업 및 키보드 동작을 추가해야 한다.

### [추가 마크업](https://www.w3.org/WAI/tutorials/menus/application-menus/#additional-markup)

- `aria-expanded`, `aria-haspopup` 속성 외에도 애플리케이션 메뉴에 필요한 시맨틱을 제공하기 위해 다음과 같은 WAI-ARIA 역할을 사용한다.
  - `menubar`: (일반적으로 가로) 메뉴 막대
  - `menu`: 드롭다운 메뉴로 사용하는 메뉴 바의 링크 또는 명령 집합
  - `menuitem`: 개별 메뉴 항목
  - `separator`: 메뉴에서 두 메뉴 항목 그룹 사이의 구분 기호
- 코드
  ```html
  <ul role="menubar" id="appmenu">
    …
    <li role="menuitem" aria-haspopup="true">
      Edit
      <ul role="menu">
        <li role="menuitem">Undo</li>
        <li role="menuitem">Redo</li>
        <li role="separator"></li>
        <li role="menuitem">Cut</li>
        <li role="menuitem">Copy</li>
        <li role="menuitem">Paste</li>
      </ul>
    </li>
    …
  </ul>
  ```
- 애플리케이션 메뉴에는 일반적으로 링크가 없으며 기능을 제공하기 위해 스크립트에 의존한다.

### [기능](https://www.w3.org/WAI/tutorials/menus/application-menus/#functionality)

- WAI-ARIA 역할을 추가한다고 해서 메뉴의 기능이나 키보드 동작을 자동으로 활성화하는 것은 아니다.
- 이러한 기능은 스크립트를 사용하여 추가해야 한다.
- WAI-ARIA 속성과 키보드 동작에 대한 자세한 설명은 [WAI-ARIA 저작 관행 문서(초안)](https://www.w3.org/TR/wai-aria-practices/#menu)에서 확인할 수 있다.

### [키보드 동작](https://www.w3.org/WAI/tutorials/menus/application-menus/#keyboard-behavior)

- 웹 애플리케이션 메뉴는 데스크톱 애플리케이션 메뉴처럼 작동해야 한다.
- 예를 들어 좌우 키는 최상위 항목을 순회하는 데 사용하며 위아래 화살표 키는 하위 메뉴를 탐색하는 데 사용한다.
- 탭 키를 누르면 다음 메뉴 항목이 아닌 메뉴 뒤의 다음 항목으로 포커스가 이동한다.
- 키보드로 메뉴 항목에 초점을 설정할 수 있게 하려면 해당 항목에 `-1` 값의 `tabindex` 속성을 부여한다.
- 첫 번째 주 메뉴 항목([예제](https://www.w3.org/WAI/tutorials/menus/application-menus-code/)에서는 'File')에는 `tabindex` 속성에 값 `0`을 할당하여 항목을 탭 순서에 추가하고 사용자가 키보드를 사용하여 메뉴에 접근할 수 있도록 한다.
- 코드

  ```Javascript
  Array.prototype.forEach.call(appsMenuItems, function(el, i){
      if (0 == i) {
        el.setAttribute('tabindex', '0');
        el.addEventListener("focus", function() {
          currentIndex = 0;
        });
      } else {
        el.setAttribute('tabindex', '-1');
      }
  });

  Array.prototype.forEach.call(subMenuItems, function(el, i){
    el.setAttribute('tabindex', '-1');
  });
  ```

### [최상위 메뉴 항목](https://www.w3.org/WAI/tutorials/menus/application-menus/#top-level-menu-items)

- 아래 표에서는 최상위 메뉴 항목의 일반적인 동작을 요약한다.

#### 최상위 메뉴 항목의 키 매핑

| 키                               | 동작                                           |
| -------------------------------- | ---------------------------------------------- |
| Tab                              | 메뉴 바깥의 포커스 가능한 다음 요소를 선택     |
| Shift+Tab                        | 메뉴 바깥의 포커스 가능한 이전 요소를 선택     |
| Right                            | 다음 최상위 메뉴 항목을 선택                   |
| Left                             | 이전 최상위 메뉴 항목을 선택                   |
| Return/Enter<br/>Space<br />Down | 하위 메뉴를 열고 첫 번째 하위 메뉴 항목을 선택 |
| Up                               | 하위 메뉴를 열고 이전 하위 메뉴 항목을 선택    |
| Esc                              | 메뉴를 종료                                    |

### [하위 메뉴 항목](https://www.w3.org/WAI/tutorials/menus/application-menus/#submenu-items)

아래 표에서는 하위 메뉴 항목의 일반적인 동작을 요약한다.

#### 하위 메뉴 항목의 키 매핑

| 키                     | 동작                                                                                         |
| ---------------------- | -------------------------------------------------------------------------------------------- |
| Tab                    | 하위 메뉴를 닫고 메뉴 바깥의 포커스 가능한 다음 요소를 선택                                  |
| Shift+Tab              | 하위 메뉴를 닫고 메뉴 바깥의 포커스 가능한 이전 요소를 선택                                  |
| Right                  | 하위 메뉴를 닫고 다음 최상위 메뉴 항목의 첫 번째 항목을 선택                                 |
| Left                   | 하위 메뉴를 닫고 이전 최상위 메뉴 항목의 첫 번째 항목을 선택                                 |
| Return/Enter<br/>Space | 이 항목의 기능을 수행(예제 기준으로 선택한 메뉴 항목의 텍스트가 포함된 대화 상자를 불러오기) |
| Down                   | 다음 하위 메뉴 항목을 선택                                                                   |
| Up                     | 이전 하위 메뉴 항목을 선택                                                                   |
| Esc                    | 하위 메뉴를 닫고 현재 최상위 메뉴 항목을 선택                                                |

## [애플리케이션 메뉴 예시 & 코드](https://www.w3.org/WAI/tutorials/menus/application-menus-code/)
