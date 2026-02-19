# [캐러셀 튜토리얼](https://www.w3.org/WAI/tutorials/carousels/)

### 캐러셀이란?

캐러셀은 여러 항목을 하나씩 보여주는 방식이다. "슬라이드 쇼"나 "슬라이더"라고도 불린다. 캐러셀의 일반적인 사용 예로는 스크롤링 뉴스 헤드라인, 홈페이지의 추천 아티클, 이미지 갤러리 등이 있다.

### 접근성 있는 캐러셀이란?

- 사용자들이 캐러셀의 움직임을 멈출 수 있어야 한다. 너무 빠르거나 산만하면 텍스트를 읽기 어려울 수 있기 때문이다.
- 캐러셀 항목 간의 탐색을 포함한 모든 기능이 키보드로 작동 가능해야 한다.
- 캐러셀 항목의 변경 사항은 스크린 리더를 사용하는 사용자에게도 모두 전달되어야 한다.
- 키보드 포커스는 합리적이고 이해하기 쉬운 방식으로 관리되어야 한다.

**참고:** 캐러셀은 콘텐츠를 발견하기 어려워서 사용성 측면에서 논란이 있다. 접근성을 보장하면 사용성도 개선할 수 있다.

### 캐러셀 접근성, 왜 중요한가?

일반적으로 캐러셀은 눈에 띄는 위치에 있으며, 탐색을 제공하거나 페이지 콘텐츠를 보여주는 데 사용된다. 접근성 있는 캐러셀은 여러 웹사이트 사용자에게 필수적이다.

- **키보드 탐색과 음성 입력 소프트웨어 사용자**가 개별 항목 간을 탐색할 수 있다.
- **스크린 리더 사용자**가 현재 표시된 항목이 무엇인지, 그리고 항목 간 탐색 방법을 이해할 수 있다.
- **움직임에 쉽게 방해받는 사람들**이 애니메이션을 일시 정지할 수 있다.
- **더 많은 시간이 필요한 사람들**이 애니메이션을 일시 정지하여 캐러셀 콘텐츠를 충분히 읽고 이해할 시간을 가질 수 있다.

## [캐러셀 구조](https://www.w3.org/WAI/tutorials/carousels/structure/)

구조적 마크업을 사용하면 캐러셀의 콘텐츠를 다양한 상황에서 활용할 수 있다. 예를 들어, 적절한 마크업이 적용된 캐러셀은 모바일 기기에서 아티클 목록으로 표시할 수 있다.

### 일반적인 구조

캐러셀은 콘텐츠 항목을 모아 놓은 것이므로, 보통 `<ul>`과 `<li>`를 사용해 비순서 목록으로 표현하는 것이 가장 좋다. 상황에 따라 다른 요소를 사용할 수도 있다.

모든 캐러셀에는 사용자가 쉽게 찾을 수 있도록 레이블이 지정된 영역을 설정해야 한다. 아래 예제에서는 `<section>` 요소로 영역을 정의하고, `aria-labelledby` 속성으로 라벨이 있는 제목을
설정한다.

[페이지 구조 튜토리얼](https://www.w3.org/WAI/tutorials/page-structure/regions/)
에서 [영역](https://www.w3.org/WAI/tutorials/page-structure/regions/)
과 [레이블](https://www.w3.org/WAI/tutorials/page-structure/labels/)에 대한 자세한 설명을 확인할 수 있다.

###### 코드

```html
<section class="carousel" aria-labelledby="carouselheading">
  <h3 id="carouselheading" class="visuallyhidden">Recent news</h3>
  <ul>
    <li class="slide">…</li>
    <li class="slide">…</li>
    <li class="slide">…</li>
    …
  </ul>
</section>
```

이 코드의 [실습 예제](https://www.w3.org/WAI/tutorials/carousels/working-example/)를 볼 수 있다.

### 캐러셀 항목

캐러셀은 보통 이미지 시리즈를 보여주는 갤러리로 사용된다. 하지만 티저, 아티클, 웹 페이지의 전체 섹션처럼 더 복잡한 콘텐츠를 캐러셀 안에 포함할 수도 있다. 어떤 경우에도, 적절한 마크업을 사용해 콘텐츠의 구조와
의미를 명확하게 전달해야 한다. 여기에는 제목, 섹션, 목록, 아티클 등의 요소가 포함될 수 있다.

첫 번째 예제는 이미지를 콘텐츠로 사용하는 캐러셀 항목을 보여준다.

###### 코드: 예제 1

```html
…
<li class="slide">
  <img src="teddy1.jpg" alt="Space Teddy" />
</li>
…
```

다음 예제는 제목과 단락이 포함된 아티클을 보여주며, 더 복잡한 콘텐츠를 어떻게 사용할 수 있는지 설명한다.

###### 코드: 예제 2

```html
…
<li class="slide" style="background-image: url('teddy1.jpg');">
  <article>
    <h4>Space Teddy production reaches all-time high</h4>
    <p>
      Teddies in Space Inc. has released outstanding numbers for the last solar
      year. The production of Space Teddies increased by 17%. The new version,
      scheduled to be released in a few months, will likely be the biggest Space
      Teddy release ever.
    </p>
    …
  </article>
</li>
…
```

## [기능](https://www.w3.org/WAI/tutorials/carousels/functionality/)

캐러셀 항목을 선택할 수 있는 기능과 항목 변경 시 사용자에게 이를 알리는 기능을 제공해야 한다.

### 이전 및 다음 버튼 추가

사용자가 항목 간에 앞뒤로 이동할 수 있도록 버튼을 제공해야 한다. `<button>` 요소를 사용해 의미를 명확히 하고, 보조 기술의 지원을 받을 수 있도록 하며 일관된 키보드 동작을 제공할 수 있다. 버튼은
자바스크립트로 생성하고 추가하는데, 어차피 자바스크립트가 있어야 버튼이 작동하기 때문이다.

###### 코드: 자바스크립트

```js
var ctrls = document.createElement("ul");

ctrls.className = "controls";
ctrls.innerHTML =
  "<li>" +
  '<button type="button" class="btn-prev">' +
  '<img src="img/chevron-left.png" alt="Previous Item">' +
  "</button>" +
  "</li>" +
  "<li>" +
  '<button type="button" class="btn-next">' +
  '<img src="img/chevron-right.png" alt="Next Item">' +
  "</button>" +
  "</li>";

ctrls.querySelector(".btn-prev").addEventListener("click", function () {
  prevSlide(true);
});

ctrls.querySelector(".btn-next").addEventListener("click", function () {
  nextSlide(true);
});

carousel.appendChild(ctrls);
```

이 코드의 [실습 예제](https://www.w3.org/WAI/tutorials/carousels/working-example/)를 볼 수 있다.

### 현재 항목 알리기

스크린 리더 사용자를 위해 현재 표시되고 있는 항목을 알리려면 [WAI-ARIA 라이브 영역](https://www.w3.org/TR/wai-aria-1.1/#live_region_roles)을 사용한다. 이
예제에서는 시각적으로는 숨겨져 있지만, "polite" 라이브 영역이 사용되며 캐러셀이 로드될 때 이 영역이 추가된다. 그런 다음 이전 또는 다음 버튼을 클릭하면 "Item x of y"라는 텍스트(여기서 x는 현재
항목 번호, y는 항목 수)가 이 라이브 영역에 설정된다. 지원되는 스크린 리더는 이 텍스트를 안내한다.

사용자가 키보드 포커스를 유지할 수 있도록 해야 한다. 캐러셀이 자동으로 이동하더라도 사용자가 페이지에서 현재 위치를 잃지 않도록 해야 하며, 이전 또는 다음 버튼을 사용할 때 포커스를 이동시키지 않도록 한다.
포커스를 이동시키면 슬라이드를 앞뒤로 탐색하는 것이 어려워질 수 있다.

WAI-ARIA에 대한 자세한
내용은 [WAI-ARIA 개요](https://www.w3.org/WAI/standards-guidelines/aria/), [WAI-ARIA 작성 방법](https://www.w3.org/TR/wai-aria-practices-1.1/),
그리고 [명세서](https://www.w3.org/TR/wai-aria-1.1/)에서 확인할 수 있다.

###### 코드: 캐러셀에 라이브 영역 추가

```js
var liveregion = document.createElement("div");
liveregion.setAttribute("aria-live", "polite");
liveregion.setAttribute("aria-atomic", "true");
liveregion.setAttribute("class", "liveregion visuallyhidden");
carousel.appendChild(liveregion);
```

###### 코드: 라이브 영역에서 텍스트를 변경하여 해당 텍스트를 알림

```js
if (announceItem) {
  carousel.querySelector(".liveregion").textContent =
    "Item " + (new_current + 1) + " of " + slides.length;
}
```

### 탐색 버튼 추가

캐러셀의 각 항목에 해당하는 버튼을 표시하고 현재 항목을 강조해야 한다. 이를 통해 사용자는 캐러셀 콘텐츠의 개요를 확인하고, 자신이 어느 위치에 있는지 알 수 있으며, 원하는 항목으로 직접 이동할 수 있다.

아래 예제에서는 자바스크립트로 버튼 목록이 추가되며, 각 버튼에는 캐러셀 항목에 해당하는 번호가 있다. 버튼은 해당 항목과 일치하는 번호로 지정되며, 현재 캐러셀 항목에 해당하는 버튼은 시각적으로 강조되고
스크린 리더를 위해 숨겨진 텍스트도 함께 제공된다.

활성화된 캐러셀 항목을 접근 가능하게 강조하는 방법에 대한 자세한 정보는 [캐러셀 스타일링](https://www.w3.org/WAI/tutorials/carousels/styling/) 페이지에서 확인할 수 있다.

###### 코드

```html
<ul class="slidenav">
  <li>
    <button class="current" data-slide="0">
      <span class="visuallyhidden">News</span> 1
      <span class="visuallyhidden">(Current Slide)</span>
    </button>
  </li>
  <li>
    <button data-slide="1"><span class="visuallyhidden">News</span> 2</button>
  </li>
  <li>
    <button data-slide="2"><span class="visuallyhidden">News</span> 3</button>
  </li>
</ul>
```

###### 예제

<div class="box-i">
  <style>
    .slidenav li {
      display: inline-block;
    }
    .slidenav button {
      border: 2px solid #036;
      background-color: #036;
      line-height: 1em;
      height: 2em;
      width: 2em;
      font-weight: bold;
      color: #fff;
    }
    .slidenav button.current {
      border-radius: 0.5em;
      background-color: #fff;
      color: #333;
    }
    .slidenav button:hover,
    .slidenav button:focus {
      border: 2px dashed #fff;
    }
    .slidenav button.current:hover,
    .slidenav button.current:focus {
      border: 2px dashed #036;
    }
    .visuallyhidden {
      border: 0;
      clip: rect(0 0 0 0);
      height: 1px;
      margin: -1px;
      overflow: hidden;
      padding: 0;
      position: absolute;
      width: 1px;
    }
  </style>

  <ul class="slidenav as-sample">
    <li>
      <button class="current" data-slide="0" type="button">
        <span class="visuallyhidden">News</span> 1
        <span class="visuallyhidden">(Current Slide)</span>
      </button>
    </li>
    <li>
      <button data-slide="1" type="button">
        <span class="visuallyhidden">News</span> 2
      </button>
    </li>
    <li>
      <button data-slide="2" type="button">
        <span class="visuallyhidden">News</span> 3
      </button>
    </li>
  </ul>

  <style>
    .slidenav.as-sample {
      position: static;
    }
  </style>
</div>

### 선택된 캐러셀 항목에 포커스 맞추기

사용자가 탐색 버튼을 통해 항목을 선택하면, 선택된 항목에 포커스를 맞춰야 한다. 이 경우, 변경 또는 전환 후 `current` 클래스가 설정된 `<li>` 요소에 포커스를 맞춘다. 이렇게 하면 키보드와 보조 기술
사용자들이 더 쉽게 상호작용할 수 있다.

기본적으로 `<li>` 요소는 포커스를 받을 수 없지만, `tabindex` 속성을 `-1`로 설정하면 자바스크립트로 포커스를 받을 수 있게 된다.

## [애니메이션](https://www.w3.org/WAI/tutorials/carousels/animations/)

사용자에게 캐러셀 애니메이션을 제어할 수 있는 기능을 제공해야 한다. 애니메이션을 멈추는 기능은 움직임에 쉽게 방해를 받거나, 콘텐츠를 읽는 데 더 많은 시간이 필요한 사람들에게 필수적이다.

### 재생/정지 버튼 추가

사용자가 애니메이션을 멈추거나 다시 재생할 수 있도록 버튼을 제공한다. 아래 예제는 이 버튼을 어떻게 마크업할 수 있는지 보여준다. 애니메이션이 실행 중인지 아닌지에 따라 버튼의 레이블과 기능이 달라진다.

###### 코드: 애니메이션이 실행되는 동안

```html
<button data-action="stop">
  <span class="visuallyhidden">Stop Animation </span>￭
</button>
```

###### 코드: 애니메이션이 중지된 동안

```html
<button data-action="start">
  <span class="visuallyhidden">Start Animation </span>▶
</button>
```

이 코드의 [실습 예제](https://www.w3.org/WAI/tutorials/carousels/working-example/)를 볼 수 있다.

### 마우스 호버 및 키보드 포커스 시 일시 정지

캐러셀에 마우스 포인터가 올라가거나 키보드 포커스를 받을 때 애니메이션을 일시 정지한다. 마우스 호버 시 애니메이션을 멈추는 기능은 콘텐츠를 읽는 데 더 많은 시간이 필요한 사람들에게 유용하며, 캐러셀에 있는 링크를
클릭하기 쉽게 만들어준다. 키보드 사용자는 캐러셀이 멈추면 자신의 위치를 잃지 않는다.

###### 코드

```js
carousel.addEventListener("mouseenter", suspendAnimation);
carousel.addEventListener("mouseleave", startAnimation);

carousel.addEventListener("focusin", function (event) {
  if (!hasClass(event.target, "slide")) {
    suspendAnimation();
  }
});
carousel.addEventListener("focusout", function (event) {
  if (!hasClass(event.target, "slide")) {
    startAnimation();
  }
});
```

### 전환 중인 요소를 보조 기술에서 숨기기

전환이 진행되는 동안 현재 항목과 다음 항목이 동시에 보이게 된다. 이로 인해 두 항목 모두 보조 기술에서 접근 가능해지는데, 현재 항목이 사라지면 스크린 리더 사용자에게 혼란을 줄 수 있다.

아래 예제에서는 활성화되는 항목에 `in-transition` 클래스를 추가하여 항목이 표시되도록 한다. 이 항목에 `aria-hidden` 속성을 `true`로 설정해 보조 기술에서 해당 항목이 보이지 않도록
하며, 전환이 완료되면 `aria-hidden` 속성을 제거한다.

###### 코드: 자바스크립트

```js
slides[new_next].className =
  "next slide" + (transition == "next" ? " in-transition" : "");
slides[new_next].setAttribute("aria-hidden", "true");

slides[new_prev].className =
  "prev slide" + (transition == "prev" ? " in-transition" : "");
slides[new_prev].setAttribute("aria-hidden", "true");

slides[new_current].className = "current slide";
slides[new_current].removeAttribute("aria-hidden");
```

## [스타일링](https://www.w3.org/WAI/tutorials/carousels/styling/)

### 버튼 크기

적절한 크기의 버튼과 링크를 사용하고, 그 주위에 여백을 제공하여, 운동 능력이 제한된 사람들도 캐러셀을 더 쉽게 사용할 수 있도록 해야 한다. 이는 모바일 기기와 같은 터치 스크린을 사용하는 사람들에게도 유익하다.
텍스트 블록 안에 인라인으로 들어가지 않은 버튼과 링크는 최소 44×44 CSS 픽셀이어야 한다.

### 대비

![충분한 대비를 보장하기 위해 반투명 배경색을 사용하는 예제.](https://i3.wp.com/www.w3.org/WAI/content-images/tutorials/carousels/carousels-styling-contrast.png)
텍스트, 링크, 버튼의 전경과 배경 간에 충분한 대비가 유지되도록 해야 한다. 이는 텍스트나 버튼이 이미지 위에 위치할 때 특히 중요한데, 이 경우 (반)투명한 배경색을 사용하면 어떤 이미지가 사용되더라도 대비를
유지할 수 있다.

대비 요구 사항에 대한 자세한
내용은 [전경과 배경 간 충분한 대비 제공](https://www.w3.org/WAI/tips/designing/#provide-sufficient-contrast-between-foreground-and-background)
을 참고하라.

### 버튼 상태 표시

캐러셀에 추가된 탐색 버튼은 일반적으로 크기가 작기 때문에, 색상과 모양으로 상태를 표시하는 것이 중요하다(적절한 이름과 레이블 외에도). 이렇게 하면 사용자가 버튼과 그 현재 상태를 더 쉽게 구분할 수 있다.

다음 예제에서는 현재 표시되지 않은 항목과 연결된 버튼에 채워진 사각형을 사용한다. 표시된 항목의 버튼은 둥근 모서리와 반전된 색상을 가진다. 사용자가 마우스를 사용해 이러한 버튼에 커서를 올리거나 키보드로 포커스를
맞출 때, 해당 버튼의 테두리는 점선으로 표시된다.

###### 예제

```html
<div class="box-i">
  <style>
    .slidenav li {
      display: inline-block;
    }
    .slidenav button {
      border: 2px solid #036;
      background-color: #036;
      line-height: 1em;
      height: 2em;
      width: 2em;
      font-weight: bold;
      color: #fff;
    }

    .slidenav button.current {
      border-radius: 0.5em;
      background-color: #fff;
      color: #333;
    }

    .slidenav button:hover,
    .slidenav button:focus {
      border: 2px dotted #fff;
    }

    .slidenav button.current:hover,
    .slidenav button.current:focus {
      border: 2px dotted #036;
    }
  </style>

  <ul class="slidenav as-sample">
    <li>
      <button class="current" data-slide="0" type="button">
        <span class="visuallyhidden">News</span> 1
        <span class="visuallyhidden">(Current Slide)</span>
      </button>
    </li>
    <li>
      <button data-slide="1" type="button">
        <span class="visuallyhidden">News</span> 2
      </button>
    </li>
    <li>
      <button data-slide="2" type="button">
        <span class="visuallyhidden">News</span> 3
      </button>
    </li>
  </ul>

  <style>
    .slidenav.as-sample {
      position: static;
    }
  </style>
</div>
```

이 코드에 대한 [실습 데모 예제](https://www.w3.org/WAI/tutorials/carousels/working-example/)를 확인할 수 있다.

### 작은 화면/뷰포트에서

모든 텍스트가 읽을 수 있고 잘리거나 불필요하게 생략되지 않도록 해야 한다. 또한, 일부 사람들은 스와이프 제스처를 사용할 수 없기 때문에, 슬라이드를 제어할 수
있는 [탐색 버튼](https://www.w3.org/WAI/tutorials/carousels/functionality/#add-navigation-buttons)이 반드시 제공되어야 한다.

## [실습 예제](https://www.w3.org/WAI/tutorials/carousels/working-example/)

###### 전체 실습 예제

<div class="box-i">
  <h3>Featured Articles:</h3>
  <div id="c" class="active carousel with-slidenav">
    <ul>
      <li
        class="current slide"
        style="
          background-image: url('/WAI/content-images/tutorials/carousels/ex-teddy1.jpg');
        "
      >
        <h4>Space Teddy Production Reaches All-Time High</h4>
        <p>
          Teddies in Space Inc. has released outstanding numbers for the last
          solar year.
          <a href="…">Full Annual Report</a>
        </p>
      </li>
      <li
        class="next slide"
        style="
          background-image: url('/WAI/content-images/tutorials/carousels/ex-teddy2.jpg');
        "
        aria-hidden="true"
      >
        <h4>New Space Teddy Announced!</h4>
        <p>
          Space Teddy 6 wears an aluminum space suit. Sapphire glass eyes are
          first used universe-wide.
          <a href="…">Everything about the new model</a>
        </p>
      </li>
      <li
        class="prev slide"
        style="
          background-image: url('/WAI/content-images/tutorials/carousels/ex-teddy3.jpg');
        "
        aria-hidden="true"
      >
        <h4>Adventures of the Space&nbsp;Teddy</h4>
        <p>
          Using modern HTML5 technologies, the latest installment of our game
          performs great on your computer, tablet, or mobile.
          <a href="…">Play the Game here!</a>
        </p>
      </li>
    </ul>
    <ul class="controls">
      <li>
        <button type="button" class="btn-prev">
          <img
            src="/WAI/content-images/tutorials/carousels/chevron-left.png"
            alt="Previous Item"
          />
        </button>
      </li>
      <li>
        <button type="button" class="btn-next">
          <img
            src="/WAI/content-images/tutorials/carousels/chevron-right.png"
            alt="Next Item"
          />
        </button>
      </li>
    </ul>
    <ul class="slidenav">
      <li>
        <button data-action="stop">
          <span class="visuallyhidden">Stop Animation </span>￭
        </button>
      </li>
      <li>
        <button class="current" data-slide="0">
          <span class="visuallyhidden">News</span> 1
          <span class="visuallyhidden">(Current Item)</span>
        </button>
      </li>
      <li>
        <button data-slide="1" class="">
          <span class="visuallyhidden">News</span> 2
        </button>
      </li>
      <li>
        <button data-slide="2" class="">
          <span class="visuallyhidden">News</span> 3
        </button>
      </li>
    </ul>
    <div
      aria-live="polite"
      aria-atomic="true"
      class="liveregion visuallyhidden"
    >
      Item 1 of 3
    </div>
  </div>

  <style>
    .active .slide {
      display: block !important;
      visibility: hidden;
      transition: left 0.6s ease-out;
    }

    .active .slide.current {
      visibility: visible;
      left: 0;
    }

    .active .slide.next {
      left: 100%;
    }

    .active .slide.prev {
      left: -100%;
    }

    .active .slide.next.in-transition,
    .active .slide.prev.in-transition {
      visibility: visible;
    }
  </style>
</div>

## [전체 코드](https://www.w3.org/WAI/tutorials/carousels/full-code/)

###### 코드

```js
/* Focusin/out event polyfill (for Firefox) by nuxodin
 * Source: https://gist.github.com/nuxodin/9250e56a3ce6c0446efa
 */

!(function () {
  var w = window,
    d = w.document;

  if (w.onfocusin === undefined) {
    d.addEventListener("focus", addPolyfill, true);
    d.addEventListener("blur", addPolyfill, true);
    d.addEventListener("focusin", removePolyfill, true);
    d.addEventListener("focusout", removePolyfill, true);
  }
  function addPolyfill(e) {
    var type = e.type === "focus" ? "focusin" : "focusout";
    var event = new CustomEvent(type, { bubbles: true, cancelable: false });
    event.c1Generated = true;
    e.target.dispatchEvent(event);
  }
  function removePolyfill(e) {
    if (!e.c1Generated) {
      // focus after focusin, so chrome will the first time trigger two times focusin
      d.removeEventListener("focus", addPolyfill, true);
      d.removeEventListener("blur", addPolyfill, true);
      d.removeEventListener("focusin", removePolyfill, true);
      d.removeEventListener("focusout", removePolyfill, true);
    }
    setTimeout(function () {
      d.removeEventListener("focusin", removePolyfill, true);
      d.removeEventListener("focusout", removePolyfill, true);
    });
  }
})();

/*
   Carousel Prototype
   Eric Eggert for W3C
*/

var myCarousel = function () {
  "use strict";

  // Initial variables
  var carousel,
    slides,
    index,
    slidenav,
    settings,
    timer,
    setFocus,
    animationSuspended;

  // Helper function: Iterates over an array of elements
  function forEachElement(elements, fn) {
    for (var i = 0; i < elements.length; i++) fn(elements[i], i);
  }

  // Helper function: Remove Class
  function removeClass(el, className) {
    if (el.classList) {
      el.classList.remove(className);
    } else {
      el.className = el.className.replace(
        new RegExp(
          "(^|\\b)" + className.split(" ").join("|") + "(\\b|$)",
          "gi"
        ),
        " "
      );
    }
  }

  // Helper function: Test if element has a specific class
  function hasClass(el, className) {
    if (el.classList) {
      return el.classList.contains(className);
    } else {
      return new RegExp("(^| )" + className + "( |$)", "gi").test(el.className);
    }
  }

  // Initialization for the carousel
  // Argument: set = an object of settings
  // Possible settings:
  // id <string> ID of the carousel wrapper element (required).
  // slidenav <bool> If true, a list of slides is shown.
  // animate <bool> If true, the slides can be animated.
  // startAnimated <bool> If true, the animation begins
  //                        immediately.
  //                      If false, the animation needs
  //                        to be initiated by clicking
  //                        the play button.
  function init(set) {
    // Make settings available to all functions
    settings = set;

    // Select the element and the individual slides
    carousel = document.getElementById(settings.id);
    slides = carousel.querySelectorAll(".slide");

    carousel.className = "active carousel";

    // Create unordered list for controls, and attach click events to previous and next slide
    var ctrls = document.createElement("ul");

    ctrls.className = "controls";
    ctrls.innerHTML =
      "<li>" +
      '<button type="button" class="btn-prev"><img src="chevron-left.png" alt="Previous Item"></button>' +
      "</li>" +
      "<li>" +
      '<button type="button" class="btn-next"><img src="chevron-right.png" alt="Next Item"></button>' +
      "</li>";

    ctrls.querySelector(".btn-prev").addEventListener("click", function () {
      prevSlide(true);
    });
    ctrls.querySelector(".btn-next").addEventListener("click", function () {
      nextSlide(true);
    });

    carousel.appendChild(ctrls);

    // If the carousel is animated or a slide navigation is requested in the settings, another unordered list that contains those elements is added. (Note that you cannot supress the navigation when it is animated.)
    if (settings.slidenav || settings.animate) {
      slidenav = document.createElement("ul");

      slidenav.className = "slidenav";

      if (settings.animate) {
        var li = document.createElement("li");

        if (settings.startAnimated) {
          li.innerHTML =
            '<button data-action="stop"><span class="visuallyhidden">Stop Animation </span>￭</button>';
        } else {
          li.innerHTML =
            '<button data-action="start"><span class="visuallyhidden">Start Animation </span>▶</button>';
        }

        slidenav.appendChild(li);
      }

      if (settings.slidenav) {
        forEachElement(slides, function (el, i) {
          var li = document.createElement("li");
          var klass = i === 0 ? 'class="current" ' : "";
          var kurrent =
            i === 0
              ? ' <span class="visuallyhidden">(Current Item)</span>'
              : "";

          li.innerHTML =
            "<button " +
            klass +
            'data-slide="' +
            i +
            '"><span class="visuallyhidden">News</span> ' +
            (i + 1) +
            kurrent +
            "</button>";
          slidenav.appendChild(li);
        });
      }

      slidenav.addEventListener(
        "click",
        function (event) {
          var button = event.target;
          if (button.localName == "button") {
            if (button.getAttribute("data-slide")) {
              stopAnimation();
              setSlides(button.getAttribute("data-slide"), true);
            } else if (button.getAttribute("data-action") == "stop") {
              stopAnimation();
            } else if (button.getAttribute("data-action") == "start") {
              startAnimation();
            }
          }
        },
        true
      );

      carousel.className = "active carousel with-slidenav";
      carousel.appendChild(slidenav);
    }

    // Add a live region to announce the slide number when using the previous/next buttons
    var liveregion = document.createElement("div");
    liveregion.setAttribute("aria-live", "polite");
    liveregion.setAttribute("aria-atomic", "true");
    liveregion.setAttribute("class", "liveregion visuallyhidden");
    carousel.appendChild(liveregion);

    // After the slide transitioned, remove the in-transition class, if focus should be set, set the tabindex attribute to -1 and focus the slide.
    slides[0].parentNode.addEventListener("transitionend", function (event) {
      var slide = event.target;
      removeClass(slide, "in-transition");
      if (hasClass(slide, "current")) {
        if (setFocus) {
          slide.setAttribute("tabindex", "-1");
          slide.focus();
          setFocus = false;
        }
      }
    });

    // When the mouse enters the carousel, suspend the animation.
    carousel.addEventListener("mouseenter", suspendAnimation);

    // When the mouse leaves the carousel, and the animation is suspended, start the animation.
    carousel.addEventListener("mouseleave", function (event) {
      if (animationSuspended) {
        startAnimation();
      }
    });

    // When the focus enters the carousel, suspend the animation
    carousel.addEventListener("focusin", function (event) {
      if (!hasClass(event.target, "slide")) {
        suspendAnimation();
      }
    });

    // When the focus leaves the carousel, and the animation is suspended, start the animation
    carousel.addEventListener("focusout", function (event) {
      if (!hasClass(event.target, "slide") && animationSuspended) {
        startAnimation();
      }
    });

    // Set the index (=current slide) to 0 – the first slide
    index = 0;
    setSlides(index);

    // If the carousel is animated, advance to the
    // next slide after 5s
    if (settings.startAnimated) {
      timer = setTimeout(nextSlide, 5000);
    }
  }

  // Function to set a slide the current slide
  function setSlides(new_current, setFocusHere, transition, announceItemHere) {
    // Focus, transition and announce Item are optional parameters.
    // focus denotes if the focus should be set after the
    // carousel advanced to slide number new_current.
    // transition denotes if the transition is going into the
    // next or previous direction.
    // If announceItem is set to true, the live region’s text is changed (and announced)
    // Here defaults are set:

    setFocus = typeof setFocusHere !== "undefined" ? setFocusHere : false;
    transition = typeof transition !== "undefined" ? transition : "none";
    announceItem =
      typeof announceItemHere !== "undefined" ? announceItemHere : false;

    new_current = parseFloat(new_current);

    var length = slides.length;
    var new_next = new_current + 1;
    var new_prev = new_current - 1;

    // If the next slide number is equal to the length,
    // the next slide should be the first one of the slides.
    // If the previous slide number is less than 0.
    // the previous slide is the last of the slides.
    if (new_next === length) {
      new_next = 0;
    } else if (new_prev < 0) {
      new_prev = length - 1;
    }

    // Reset slide classes
    for (var i = slides.length - 1; i >= 0; i--) {
      slides[i].className = "slide";
    }

    // Add classes to the previous, next and current slide
    slides[new_next].className =
      "next slide" + (transition == "next" ? " in-transition" : "");
    slides[new_next].setAttribute("aria-hidden", "true");

    slides[new_prev].className =
      "prev slide" + (transition == "prev" ? " in-transition" : "");
    slides[new_prev].setAttribute("aria-hidden", "true");

    slides[new_current].className = "current slide";
    slides[new_current].removeAttribute("aria-hidden");

    // Update the text in the live region which is then announced by screen readers.
    if (announceItem) {
      carousel.querySelector(".liveregion").textContent =
        "Item " + (new_current + 1) + " of " + slides.length;
    }

    // Update the buttons in the slider navigation to match the currently displayed  item
    if (settings.slidenav) {
      var buttons = carousel.querySelectorAll(".slidenav button[data-slide]");
      for (var j = buttons.length - 1; j >= 0; j--) {
        buttons[j].className = "";
        buttons[j].innerHTML =
          '<span class="visuallyhidden">News</span> ' + (j + 1);
      }
      buttons[new_current].className = "current";
      buttons[new_current].innerHTML =
        '<span class="visuallyhidden">News</span> ' +
        (new_current + 1) +
        ' <span class="visuallyhidden">(Current Item)</span>';
    }

    // Set the global index to the new current value
    index = new_current;
  }

  // Function to advance to the next slide
  function nextSlide(announceItem) {
    announceItem = typeof announceItem !== "undefined" ? announceItem : false;

    var length = slides.length,
      new_current = index + 1;

    if (new_current === length) {
      new_current = 0;
    }

    // If we advance to the next slide, the previous needs to be
    // visible to the user, so the third parameter is 'prev', not
    // next.
    setSlides(new_current, false, "prev", announceItem);

    // If the carousel is animated, advance to the next
    // slide after 5s
    if (settings.animate) {
      timer = setTimeout(nextSlide, 5000);
    }
  }

  // Function to advance to the previous slide
  function prevSlide(announceItem) {
    announceItem = typeof announceItem !== "undefined" ? announceItem : false;

    var length = slides.length,
      new_current = index - 1;

    // If we are already on the first slide, show the last slide instead.
    if (new_current < 0) {
      new_current = length - 1;
    }

    // If we advance to the previous slide, the next needs to be
    // visible to the user, so the third parameter is 'next', not
    // prev.
    setSlides(new_current, false, "next", announceItem);
  }

  // Function to stop the animation
  function stopAnimation() {
    clearTimeout(timer);
    settings.animate = false;
    animationSuspended = false;
    _this = carousel.querySelector("[data-action]");
    _this.innerHTML = '<span class="visuallyhidden">Start Animation </span>▶';
    _this.setAttribute("data-action", "start");
  }

  // Function to start the animation
  function startAnimation() {
    settings.animate = true;
    animationSuspended = false;
    timer = setTimeout(nextSlide, 5000);
    _this = carousel.querySelector("[data-action]");
    _this.innerHTML = '<span class="visuallyhidden">Stop Animation </span>￭';
    _this.setAttribute("data-action", "stop");
  }

  // Function to suspend the animation
  function suspendAnimation() {
    if (settings.animate) {
      clearTimeout(timer);
      settings.animate = false;
      animationSuspended = true;
    }
  }

  // Making some functions public
  return {
    init: init,
    next: nextSlide,
    prev: prevSlide,
    goto: setSlides,
    stop: stopAnimation,
    start: startAnimation,
  };
};

var carousel = new myCarousel();
carousel.init({
  id: "carousel",
  slidenav: true,
  animate: true,
  startAnimated: true,
});
```
