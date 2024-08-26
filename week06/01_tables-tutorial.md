# [표 튜토리얼](https://www.w3.org/WAI/tutorials/tables/)

데이터 표는 그리드에서 논리 관계로 데이터를 구성하는 데 사용한다.
접근성 있는 표에는 헤더 셀과 데이터 셀을 나타내고 관계를 정의하는 HTML 마크업이 필요하다.
보조 기술은 이 정보를 사용하여 사용자에게 컨텍스트를 제공한다.

헤더 셀은 `<th>`로, 데이터 셀은 `<td>`로 마크업해야 표를 접근성이 있게 만들 수 있다.
보다 복잡한 표의 경우 `scope`, `id`, `header` 속성을 사용하여 명시적으로 연결해야 할 수 있다.

이 튜토리얼에서는 표에 적절한 구조적 마크업을 적용하는 방법을 보여준다.

PDF와 같은 HTML 이외의 일부 문서 형식은 표 구조와 유사한 메커니즘을 제공한다.
워드 프로세싱 애플리케이션에서도 표를 마크업하는 메커니즘을 제공할 수 있다.
일부 프로그램에서는 표 마크업 변환을 지원하는 기능을 제공할 수 있지만, 한 형식에서 다른 형식으로 변환할 때 표 마크업이 손실되는 경우가 많다.

많은 웹 작성 도구 및 콘텐츠 관리 시스템(CMS)은 코드를 수동으로 편집하지 않고도 표를 만드는 동안 헤더 셀을 정의할 수 있는 기능을 제공한다.

> 참고
>
> 이 튜토리얼에서는 그리드에 데이터를 표시하는 데 사용되는 표를 만드는 방법에 대한 지침을 제공한다.
> 이 튜토리얼은 레이아웃에 사용되는 표에는 적용되지 않는다.
> 일반적으로 표는 레이아웃 용도로 사용되지 않는다.
> 대신 시각적 프레젠테이션을 위해 CSS(Cascading Style Sheet)를 사용하는 것이 가장 좋다.

## [표, 왜 중요할까?](https://www.w3.org/WAI/tutorials/tables/#why-is-this-important)

헤더와 데이터 셀을 구분하고 적절하게 연결하기 위한 구조적 마크업이 없는 표는 접근성을 차단하는 장벽을 만든다.
시각적 단서에만 의존하는 것만으로는 접근성 있는 표를 만드는 데 충분하지 않다.
구조적 마크업을 사용하면 헤더와 데이터 셀을 소프트웨어에서 프로그래밍 방식으로 결정할 수 있다.

- **스크린 리더 사용자**는 표를 탐색할 때 행과 열 헤더를 소리내어 읽을 수 있다.
  스크린 리더는 한 번에 한 셀씩 말하며 관련 헤더 셀을 참조하므로 독자가 컨텍스트를 잃지 않는다.
- 사용자 정의 스타일시트를 사용하여 헤더 셀을 더 눈에 띄게 표시하는 등 **다른 방법으로 데이터를 렌더링하는 사람들이 있다.**
  이러한 기술을 사용하면 텍스트 크기와 색상을 변경하고 정보를 그리드가 아닌 목록으로 표시할 수 있다.
  대체 렌더링을 허용하려면 표 코드가 적절하게 구조화되어 있어야 한다.

## [헤더가 하나인 표](https://www.w3.org/WAI/tutorials/tables/one-header/)

이 페이지에서는 행에 대한 간단한 헤더 하나 또는 열에 대한 간단한 헤더 하나가 있는 표를 다룬다.
이러한 표의 데이터는 그 자체로 설명적이며 모호하지 않다.

표 콘텐츠가 모호하거나 열과 행 헤더가 모두 있는 경우 혼동을 피하기 위해 `scope` 속성을 사용해야 한다.
이러한 표에 대한 자세한 지침은 [헤더가 둘인 표](https://www.w3.org/WAI/tutorials/two-headers/)에서 확인할 수 있다.

### [예제 1: 맨 위 행에만 헤더 셀이 있는 표](https://www.w3.org/WAI/tutorials/tables/one-header/#table-with-header-cells-in-the-top-row-only)

다음 콘서트 표에는 첫 번째 행의 셀이 `<th>` 요소를 사용하여 마크업되어 있다.
이 표는 매우 작은 표이고 데이터 자체가 각 열에서 뚜렷하게 달라 헤더와 데이터 셀 간의 관계가 분명하기 때문에 가능하다.

> 참고
>
> 일부 스크린 리더는 `<th>` 요소의 방향이 모호하기 때문에 "장소" 셀에서 "날짜-이벤트-장소"를 읽는다.

#### 예제

<div class="box-i">

<p><strong>Concerts:</strong></p>
<table>
  <tbody><tr>
    <th>Date</th>
    <th>Event</th>
    <th>Venue</th>
  </tr>
  <tr>
    <td>12 February</td>
    <td>Waltz with Strauss</td>
    <td>Main Hall</td>
  </tr>
  <tr>
    <td>24 March</td>
    <td>The Obelisks</td>
    <td>West Wing</td>
  </tr>
  <tr>
    <td>14 April</td>
    <td>The What</td>
    <td>Main Hall</td>
  </tr>
</tbody></table>

</div>

#### 코드 스니펫

```html
<table>
  <tr>
    <th>Date</th>
    <th>Event</th>
    <th>Venue</th>
  </tr>
  <tr>
    <td>12 February</td>
    <td>Waltz with Strauss</td>
    <td>Main Hall</td>
  </tr>
  […]
</table>
```

### [예제 2: 첫 번째 열에만 헤더 셀이 있는 표](https://www.w3.org/WAI/tutorials/tables/one-header/#table-with-header-cells-in-the-first-column-only)

아래 표에서는 이전 예제의 데이터가 왼쪽에 헤더 열로 배치되어 있다.
이 상황에서도 작고 간단한 표이기 때문에 이 코드를 사용할 수 있다.
이 튜토리얼의 다음 페이지에서는 더 복잡한 표의 코드를 작성하는 방법을 설명한다.

#### 예제

<div class="box-i">

<p><strong>Concerts:</strong></p>
<table>
  <tbody><tr>
    <th>Date</th>
    <td>12 February</td>
    <td>24 March</td>
    <td>14 April</td>
  </tr>
  <tr>
    <th>Event</th>
    <td>Waltz with Strauss</td>
    <td>The Obelisks</td>
    <td>The What</td>
  </tr>
  <tr>
    <th>Venue</th>
    <td>Main Hall</td>
    <td>West Wing</td>
    <td>Main Hall</td>
  </tr>
</tbody></table>

</div>

#### 코드 스니펫

```html
<table>
  <tr>
    <th>Date</th>
    <td>12 February</td>
    <td>24 March</td>
    <td>14 April</td>
  </tr>
  <tr>
    <th>Event</th>
    <td>Waltz with Strauss</td>
    <td>The Obelisks</td>
    <td>The What</td>
  </tr>
  <tr>
    <th>Venue</th>
    <td>Main Hall</td>
    <td>West Wing</td>
    <td>Main Hall</td>
  </tr>
</table>
```

### [예제 3: 모호한 데이터가 있는 표](https://www.w3.org/WAI/tutorials/tables/one-header/#table-with-ambiguous-data)

이 예제에서는 데이터(이름, 성, 도시)가 각각 어느 헤더에 해당하는지 알지 못하면 서로 구별할 수 없다.
`col` 값이 있는 `scope` 속성은 헤더 셀의 방향을 정의하고 해당 데이터 셀과 연결한다.
`scope` 속성은 헤더 행 또는 열이 하나인 큰 표에도 필요하다.

#### 예제

<table>
  <caption>Teddy bear collectors:</caption>
  <tbody><tr>
    <th scope="col">Last Name</th>
    <th scope="col">First Name</th>
    <th scope="col">City</th>
  </tr>
  <tr>
    <td>Phoenix</td>
    <td>Imari</td>
    <td>Henry</td>
  </tr>
  <tr>
    <td>Zeki</td>
    <td>Rome</td>
    <td>Min</td>
  </tr>
  <tr>
    <td>Apirka</td>
    <td>Kelly</td>
    <td>Brynn</td>
  </tr>
</tbody></table>

#### 코드 스니펫

```html
<table>
  <caption>
    Teddy bear collectors:
  </caption>
  <tr>
    <th scope="col">Last Name</th>
    <th scope="col">First Name</th>
    <th scope="col">City</th>
  </tr>
  <tr>
    <td>Phoenix</td>
    <td>Imari</td>
    <td>Henry</td>
  </tr>
  <tr>
    <td>Zeki</td>
    <td>Rome</td>
    <td>Min</td>
  </tr>
  <tr>
    <td>Apirka</td>
    <td>Kelly</td>
    <td>Brynn</td>
  </tr>
</table>
```

## [헤더가 둘인 표](https://www.w3.org/WAI/tutorials/tables/two-headers/)

이 페이지에서는 간단한 행 헤더와 간단한 열 헤더가 있는 표를 다룬다.
이러한 표에서는 헤더와 데이터 셀 간의 관계가 금방 모호해진다.
이러한 표의 경우 `<th>` 요소를 사용하여 헤더 셀을 식별하고 `scope` 속성을 사용하여 각 헤더의 방향을 선언한다.
`scope` 속성을 `row` 또는 `col`로 설정하여 헤더가 전체 행 또는 열에 각각 적용됨을 나타낼 수 있다.

또한 `<caption>` 요소를 사용하여 문서에서 표를 식별할 수 있다.
이 기능은 표에서 표로 이동할 수 있는 "표 모드"에서 웹 페이지를 탐색하는 스크린 리더 사용자에게 특히 유용하다.
`<caption>` 요소 사용에 대한 자세한 배경 및 지침은 [캡션 및 요약 페이지](https://www.w3.org/WAI/tutorials/tables/caption-summary/)에서 확인할 수 있다.

### [예제 1: 맨 위 행과 첫 번째 열에 헤더 셀이 있는 표](https://www.w3.org/WAI/tutorials/tables/two-headers/#table-with-header-cells-in-the-top-row-and-first-column)

아래 여는 시간 표에는 맨 위 행과 첫 번째 열 모두에 헤더 정보가 있다.
모든 헤더 셀은 `scope` 속성이 추가된 `<th>` 셀로 마크업된다.

헤더 행에서 `scope`의 `col` 값은 각 헤더 셀을 열의 데이터 셀과 연결한다.
헤더 열에서 `row` 값은 개별 헤더를 해당 행과 연결한다.
이 정보가 없으면 일부 사용자는 헤더와 데이터 셀 간의 관계를 쉽게 이해하지 못할 수 있다.
아래 예제에서 "Open" 및 "Closed" 레이블은 특정 요일과 시간에 할당할 수 있는 경우에만 유용하다.

#### 예제

<table>
  <caption>Delivery slots:</caption>
  <tbody><tr>
    <td></td>
    <th scope="col">Monday</th>
    <th scope="col">Tuesday</th>
    <th scope="col">Wednesday</th>
    <th scope="col">Thursday</th>
    <th scope="col">Friday</th>
  </tr>
  <tr>
    <th scope="row">09:00 – 11:00</th>
    <td>Closed</td>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  <tr>
    <th scope="row">11:00 – 13:00</th>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  <tr>
    <th scope="row">13:00 – 15:00</th>
    <td>Open</td>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  <tr>
    <th scope="row">15:00 – 17:00</th>
    <td>Closed</td>
    <td>Closed</td>
    <td>Closed</td>
    <td>Open</td>
    <td>Open</td>
  </tr>
</tbody></table>

#### 코드 스니펫

```html
<table>
  <caption>
    Delivery slots:
  </caption>
  <tr>
    <td></td>
    <th scope="col">Monday</th>
    <th scope="col">Tuesday</th>
    <th scope="col">Wednesday</th>
    <th scope="col">Thursday</th>
    <th scope="col">Friday</th>
  </tr>
  <tr>
    <th scope="row">09:00 – 11:00</th>
    <td>Closed</td>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  <tr>
    <th scope="row">11:00 – 13:00</th>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  […]
</table>
```

["맨 위 행과 첫 번째 열에 헤더 셀이 있는 표"의 전체 코드](https://www.w3.org/WAI/tutorials/tables/examples/headertoprowfirstcol/)

### [예제 2: 헤더 셀의 오프셋 열이 있는 표](https://www.w3.org/WAI/tutorials/tables/two-headers/#table-with-an-offset-column-of-header-cells)

이 표에서 행 헤더 셀은 첫 번째 열이 아닌 두 번째 열에 있다.
접근 방식은 맨 위 행의 헤더 셀의 `scope`가 `col`로 설정되어 있는 위의 예제와 유사하다.
`scope`에 `row` 값을 사용하면 두 번째 열의 헤더 셀을 개별 헤더 셀의 왼쪽과 오른쪽에 있는 데이터 셀에 할당한다.

#### 예제

<table class="numbers">
  <caption>
    Holidays taken in the last six months
  </caption>
  <thead>
    <tr>
      <th scope="col">ID</th>
      <th scope="col">Name</th>
      <th scope="col">July</th>
      <th scope="col">August</th>
      <th scope="col">September</th>
      <th scope="col">October</th>
      <th scope="col">November</th>
      <th scope="col">December</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>215</td>
      <th scope="row">Abel</th>
      <td>5</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
    </tr>

    <tr>
      <td>231</td>
      <th scope="row">Annette </th>
      <td>0</td>
      <td>5</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>6</td>
    </tr>

    <tr>
      <td>173</td>
      <th scope="row">Bernard</th>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
      <td>0</td>
    </tr>

    <tr>
      <td>141</td>
      <th scope="row">Gerald</th>
      <td>0</td>
      <td>10</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
    </tr>

    <tr>
      <td>99</td>
      <th scope="row">Michael</th>
      <td>8</td>
      <td>8</td>
      <td>8</td>
      <td>8</td>
      <td>0</td>
      <td>4</td>
    </tr>

  </tbody>
</table>

#### 코드 스니펫

```html
[…]
<tr>
  <td>215</td>
  <th scope="row">Abel</th>
  <td>5</td>
  <td>2</td>
  <td>0</td>
  <td>0</td>
  <td>0</td>
  <td>3</td>
</tr>
[…]
```

["헤더 셀의 오프셋 열이 있는 표"의 전체 코드](https://www.w3.org/WAI/tutorials/tables/examples/scope-offset/)

## [불규칙한 헤더가 있는 표](https://www.w3.org/WAI/tutorials/tables/irregular/)

이 페이지에서는 여러 열 및/또는 행에 걸쳐 있는 헤더 셀이 있는 표를 다룬다.
여러 요소와 속성을 사용하여 헤더 및 데이터 셀의 구조와 관계를 정의할 수 있다.

예를 들어 세 개의 열에 걸쳐 있는 헤더 셀은 열 그룹의 해당 데이터 셀과 연결되어야 한다.
헤더 셀의 `scope` 속성을 `colgroup` 값으로 설정하면 이 작업을 수행할 수 있다.
여러 행에 걸쳐 있는 헤더 셀에도 동일한 원칙이 적용된다.
이 경우 `scope` 속성에 `rowgroup` 값을 사용하여 연결한다.

그러나 이러한 연결을 만들기 전에 표 마크업에서 이러한 열과 행 그룹의 구조를 정의해야 한다.

- 열 그룹은 `<colgroup>` 요소를 사용하여 정의한다.
- 행 그룹은 `<thead>`, `<tfoot>` 및 `<tbody>` 요소로 정의된다.
  - `<thead>` 및 `<tfoot>` 요소는 표에서 한 번만 사용할 수 있다.
  - 표에는 각각 행 그룹을 정의하는 `<tbody>` 요소를 얼마든지 포함할 수 있다.

### [두 개의 계층 헤더가 있는 표](https://www.w3.org/WAI/tutorials/tables/irregular/#table-with-two-tier-headers)

아래 표에는 두 쌍의 열 헤더가 있다.
열 헤더의 각 쌍인 "Produced" 및 "Sold"는 해당 쌍을 식별하는 첫 번째 단계의 헤더 "Mars" 및 "Venus"와 연결되어 있다.
이러한 첫 번째 단계의 헤더는 값이 2인 `colspan` 속성을 사용하여 두 열에 걸쳐 있도록 만들어진다.

첫 번째 단계의 헤더를 두 열의 모든 셀과 올바르게 연결하려면 열 구조를 표의 시작 부분에 정의해야 한다.
`<col>` 요소는 왼쪽부터 시작하여 각 열을 식별한다.
헤더가 두 개 이상의 열에 걸쳐 있는 경우 해당 수의 `<col>` 요소 대신 `<colgroup>` 요소를 사용하면 되고, `span` 속성에 걸쳐 있는 열의 수가 표시된다.

또한 첫 번째 단계의 헤더의 `scope` 속성 값은 전체 열 그룹과 연결되도록 `colgroup`으로 설정된다.
두 번째 단계의 헤더는 해당 열에만 적용되므로 `scope` 속성은 이전 예제에서와 같이 `col`로 설정된다.

#### 예제

<table class="numbers">
  <colgroup><col>
  </colgroup><colgroup span="2"></colgroup>
  <colgroup span="2"></colgroup>
  <tbody><tr>
    <td rowspan="2"></td>
    <th colspan="2" scope="colgroup">Mars</th>
    <th colspan="2" scope="colgroup">Venus</th>
  </tr>
  <tr>
    <th scope="col">Produced</th>
    <th scope="col">Sold</th>
    <th scope="col">Produced</th>
    <th scope="col">Sold</th>
  </tr>
  <tr>
    <th scope="row">Teddy&nbsp;Bears</th>
    <td>50,000</td>
    <td>30,000</td>
    <td>100,000</td>
    <td>80,000</td>
  </tr>
  <tr>
    <th scope="row">Board&nbsp;Games</th>
    <td>10,000</td>
    <td>5,000</td>
    <td>12,000</td>
    <td>9,000</td>
  </tr>
</tbody></table>

#### 코드 스니펫

```html
<table>
  <col />
  <colgroup span="2"></colgroup>
  <colgroup span="2"></colgroup>
  <tr>
    <td rowspan="2"></td>
    <th colspan="2" scope="colgroup">Mars</th>
    <th colspan="2" scope="colgroup">Venus</th>
  </tr>
  <tr>
    <th scope="col">Produced</th>
    <th scope="col">Sold</th>
    <th scope="col">Produced</th>
    <th scope="col">Sold</th>
  </tr>
  <tr>
    <th scope="row">Teddy Bears</th>
    <td>50,000</td>
    <td>30,000</td>
    <td>100,000</td>
    <td>80,000</td>
  </tr>
  <tr>
    <th scope="row">Board Games</th>
    <td>10,000</td>
    <td>5,000</td>
    <td>12,000</td>
    <td>9,000</td>
  </tr>
</table>
```

> 참고
>
> `<colgroup>` 요소에는 그룹의 개별 열을 식별하는 `<col>` 요소가 포함될 수 있다.
> `<col>` 요소에 포함되지 않은 `<col>` 요소와 `<colgroup>` 요소의 `span` 속성으로 표시된 열 요소의 합은 표의 총 열 수와 같아야 한다.

### [여러 행 또는 열에 걸쳐 있는 헤더가 있는 표](https://www.w3.org/WAI/tutorials/tables/irregular/#table-with-headers-spanning-multiple-rows-or-columns)

아래 예제에서 표는 두 개의 개별 열과 세 개의 열에 걸쳐 있는 하나의 열 그룹으로 구성되어 있다.
6개의 행이 있고 여러 행에 걸쳐 있는 두 개의 헤더가 있다.
여러 행에 걸쳐 있는 이러한 헤더 셀이 해당 행의 모든 셀과 올바르게 연결되도록 하려면 행을 그룹화해야 한다.
행 그룹을 정의하려면 해당 행을 `<tbody>` 요소(표 본문)로 묶는다.
또한 행에 걸쳐 있는 헤더 셀의 범위 속성을 `rowgroup`으로 설정해야 한다.

헤더가 여러 헤더 행에 걸쳐 있는 경우 행을 `<tbody>` 요소 대신 `<thead>` 요소로 감싸면 된다.
헤더가 표의 푸터 영역에서 여러 행에 걸쳐 있는 경우 `<tfoot>` 요소를 사용한다.

표가 복잡하기 때문에 표의 레이아웃을 자세히 설명하기 위해 [요약 기법](https://www.w3.org/WAI/tutorials/tables/caption-summary/)을 사용할 수 있다.

#### 예제

<table>
  <caption>
    Poster availability
  </caption>
  <colgroup><col>
  <col>
  </colgroup><colgroup span="3"></colgroup>
  <thead>
    <tr>
      <th scope="col">Poster name</th>
      <th scope="col">Color</th>
      <th colspan="3" scope="colgroup">Sizes available</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3" scope="rowgroup">Zodiac</th>
      <th scope="row">Full color</th>
      <td>A2</td>
      <td>A3</td>
      <td>A4</td>
    </tr>
    <tr>
      <th scope="row">Black and white</th>
      <td>A1</td>
      <td>A2</td>
      <td>A3</td>
    </tr>
    <tr>
      <th scope="row">Sepia</th>
      <td>A3</td>
      <td>A4</td>
      <td>A5</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th rowspan="2" scope="rowgroup">Angels</th>
      <th scope="row">Black and white</th>
      <td>A1</td>
      <td>A3</td>
      <td>A4</td>
    </tr>
    <tr>
      <th scope="row">Sepia</th>
      <td>A2</td>
      <td>A3</td>
      <td>A5</td>
    </tr>
  </tbody>
</table>

#### 코드 스니펫

```html
<table>
  <caption>
    Poster availability
  </caption>
  <col />
  <col />
  <colgroup span="3"></colgroup>
  <thead>
    <tr>
      <th scope="col">Poster name</th>
      <th scope="col">Color</th>
      <th colspan="3" scope="colgroup">Sizes available</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3" scope="rowgroup">Zodiac</th>
      <th scope="row">Full color</th>
      <td>A2</td>
      <td>A3</td>
      <td>A4</td>
    </tr>
    <tr>
      <th scope="row">Black and white</th>
      <td>A1</td>
      <td>A2</td>
      <td>A3</td>
    </tr>
    <tr>
      <th scope="row">Sepia</th>
      <td>A3</td>
      <td>A4</td>
      <td>A5</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th rowspan="2" scope="rowgroup">Angels</th>
      <th scope="row">Black and white</th>
      <td>A1</td>
      <td>A3</td>
      <td>A4</td>
    </tr>
    <tr>
      <th scope="row">Sepia</th>
      <td>A2</td>
      <td>A3</td>
      <td>A5</td>
    </tr>
  </tbody>
</table>
```

[전체 코드 예제](https://www.w3.org/WAI/tutorials/tables/examples/scope-multiple/)

> 참고
>
> 열에 걸친 헤더가 없더라도 모든 표에 `<thead>`, `<tbody>` 및 `<tfoot>`를 사용하면 이들을 언제 사용해야 하는지 혼동을 피할 수 있다.

## [다단계 헤더가 있는 표](https://www.w3.org/WAI/tutorials/tables/multi-level/)

이 페이지에서는 데이터 셀당 다단계 헤더 셀이 연결된 표를 다룬다.
이러한 표는 헤더와 데이터 셀 간의 엄격한 수평 또는 수직 연결을 식별하기에는 너무 복잡하다.
이러한 표에서 각 표 헤더는 (문서 전체에 걸친) 고유 `id`로 표시된다.
데이터 셀은 `headers` 속성에 하나 이상의 `id`를 공백으로 구분하여 나열함으로써 이러한 `id`를 참조한다.

이러한 방식으로 마크업해야 하는 표에는 다음이 포함된다.

- 표 중간에 반복되거나 변경되는 열 헤더가 있는 표.
- 각 데이터 셀과 연결된 헤더 셀이 3개 이상인 표.

헤더가 여러 개 있는 표에는 표를 식별하기 위한 캡션과 표의 레이아웃을 설명하는 요약이 필요할 수도
있다([캡션 및 요약](https://www.w3.org/WAI/tutorials/tables/caption-summary/) 참조).

많은 경우, [예제 3](https://www.w3.org/WAI/tutorials/tables/multi-level/#split-up-multi-level-tables)과 같이 정보를 더 작고 관리하기 쉬운 표로
분할하는 등 모든 독자가 덜 복잡하게 볼 수 있도록 이러한 표의 정보를 재구성하는 것이 좋다.

### [예제 1: 각 열에 여러 개의 열 헤더가 있는 표](https://www.w3.org/WAI/tutorials/tables/multi-level/#table-with-multiple-column-headers-in-each-column)

아래 표에서 표의 위쪽 절반의 헤더가 아래쪽 절반의 헤더와 다르다.
표 중간에 헤더가 변경되어 열의 헤더가 모호해진다.
각 데이터 셀이 올바른 헤더에 연결되도록 하기 위해 각 `<th>` 요소에는 고유 `id`가 있고 각 `<td>` 셀에는 연결된 헤더 셀의 `id` 값을 나열하는 `headers` 속성이 있다.

#### 예제

<table>
  <caption>
    Supplier contacts
  </caption>
  <tbody><tr>
    <td id="blank">&nbsp;</td>
    <th id="co1" headers="blank">Example 1 Ltd</th>
    <th id="co2" headers="blank">Example 2 Co</th>
  </tr>
  <tr>
    <th id="c1" headers="blank">Contact</th>
    <td headers="co1 c1">James Phillips</td>
    <td headers="co2 c1">Marie Beauchamp</td>
  </tr>
  <tr>
    <th id="p1" headers="blank">Position</th>
    <td headers="co1 p1">Sales Director</td>
    <td headers="co2 p1">Sales Manager</td>
  </tr>
  <tr>
    <th id="e1" headers="blank">Email</th>
    <td headers="co1 e1">jp@1ltd.example.com</td>
    <td headers="co2 e1">marie@2co.example.com</td>
  </tr>
  <tr>
    <td>&nbsp;</td>
    <th id="co3" headers="blank">Example 3 Ltd</th>
    <th id="co4" headers="blank">Example 4 Inc</th>
  </tr>
  <tr>
    <th id="c2" headers="blank">Contact</th>
    <td headers="co3 c2">Suzette Jones</td>
    <td headers="co4 c2">Alex Howe</td>
  </tr>
  <tr>
    <th id="p2" headers="blank">Position</th>
    <td headers="co3 p2">Sales Officer</td>
    <td headers="co4 p2">Sales Director</td>
  </tr>
  <tr>
    <th id="e2" headers="blank">Email</th>
    <td headers="co3 e2">Suz@ltd3.example.com</td>
    <td headers="co4 e2">howe@4inc.example.com</td>
  </tr>
</tbody></table>

아래 코드 스니펫에서는 헤더 셀 자체의 헤더가 빈 셀로 설정되어 있다(`id`가 "blank").
이렇게 하면 일부 보조 기술이 해당 헤더 셀의 헤더를 읽지 못한다.

#### 코드 스니펫: `<th>` 셀에 `id` 속성 할당

```html
[…]
<td id="blank">&nbsp;</td>
<th id="co1" headers="blank">Example 1 Ltd</th>
<th id="co2" headers="blank">Example 2 Co</th>
[…]
<th id="c1" headers="blank">Contact</th>
[…]
```

#### 코드 스니펫: `<td>` 셀에 `header` 속성 할당

```html
[…]
<td headers="co1 c1">James Phillips</td>
<td headers="co2 c1">Marie Beauchamp</td>
[…]
```

["각 열에 여러 개의 열 헤더가 있는 표" 예제의 전체 코드](https://www.w3.org/WAI/tutorials/tables/examples/multiplecolumnheaders/)

### [예제 2: 각 데이터 셀과 관련된 3개의 헤더가 있는 표](https://www.w3.org/WAI/tutorials/tables/multi-level/#table-with-three-headers-related-to-each-data-cell)

이 예제에서 표 헤더는 표의 다음 섹션에 대한 내용을 설명하는 부제목으로 사용된다.
이러한 헤더가 없으면 정보가 불분명하다.
`headers` 속성을 사용하면 세 개의 헤더를 모두 데이터 셀과 적절하게 연결할 수 있다.

#### 예제

<table class="numbers" summary="Column one has the location and size of accommodation, other columns show the type and number of properties available">
<caption>
    Availability of holiday accommodation
</caption>
<thead>
    <tr>
        <td></td>
        <th id="stud" scope="col">
            Studio
        </th>
        <th id="apt" scope="col">
            <abbr title="Apartment">Apt</abbr>
        </th>
        <th id="chal" scope="col">
            Chalet
        </th>
        <th id="villa" scope="col">
            Villa
        </th>
    </tr>
</thead>
<tbody>
    <tr>
        <th id="par" class="span" colspan="5" scope="colgroup">
            Paris
        </th>
    </tr>
    <tr>
        <th headers="par" id="pbed1">
            1 bedroom
        </th>
        <td headers="par pbed1 stud">
            11
        </td>
        <td headers="par pbed1 apt">
            20
        </td>
        <td headers="par pbed1 chal">
            25
        </td>
        <td headers="par pbed1 villa">
            23
        </td>
    </tr>
    <tr>
        <th headers="par" id="pbed2">
            2 bedroom
        </th>
        <td headers="par pbed2 stud">
            -
        </td>
        <td headers="par pbed2 apt">
            43
        </td>
        <td headers="par pbed2 chal">
            52
        </td>
        <td headers="par pbed2 villa">
            32
        </td>
    </tr>
    <tr>
        <th headers="par" id="pbed3">
            3 bedroom
        </th>
        <td headers="par pbed3 stud">
            -
        </td>
        <td headers="par pbed3 apt">
            13
        </td>
        <td headers="par pbed3 chal">
            15
        </td>
        <td headers="par pbed3 villa">
            40
        </td>
    </tr>
    <tr>
        <th id="rome" class="span" colspan="5" scope="colgroup">
            Rome
        </th>
    </tr>
    <tr>
        <th id="rbed1" headers="rome">
            1 bedroom
        </th>
        <td headers="rome rbed1 stud">
            13
        </td>
        <td headers="rome rbed1 apt">
            21
        </td>
        <td headers="rome rbed1 chal">
            22
        </td>
        <td headers="rome rbed1 villa">
            3
        </td>
    </tr>
    <tr>
        <th id="rbed2" headers="rome">
            2 bedroom
        </th>
        <td headers="rome rbed2 stud">
            -
        </td>
        <td headers="rome rbed2 apt">
            23
        </td>
        <td headers="rome rbed2 chal">
            43
        </td>
        <td headers="rome rbed2 villa">
            30
        </td>
    </tr>
    <tr>
        <th id="rbed3" headers="rome">
            3 bedroom
        </th>
        <td headers="rome rbed3 stud">
            -
        </td>
        <td headers="rome rbed3 apt">
            16
        </td>
        <td headers="rome rbed3 chal">
            32
        </td>
        <td headers="rome rbed3 villa">
            40
        </td>
    </tr>
</tbody>
</table>

#### 코드 스니펫: `<th>` 셀에 `id` 속성 할당

```html
[…]
<th id="par" colspan="5" scope="colgroup">Paris</th>
</tr>
<tr>
    <th id="pbed1">1 bedroom</th>
    […]
```

#### 코드 스니펫: `<td>` 셀에 `header` 속성 할당

```html
[…]
<td headers="par pbed1 stud">11</td>
<td headers="par pbed1 apt">20</td>
[…]
```

["각 데이터 셀과 관련된 3개의 헤더가 있는 표" 예제의 전체 코드](https://www.w3.org/WAI/tutorials/tables/examples/threeheaders/)

### [예제 3: 다단계 표 분할](https://www.w3.org/WAI/tutorials/tables/multi-level/#split-up-multi-level-tables)

아래 두 표는 [위 예제](https://www.w3.org/WAI/tutorials/tables/multi-level/#table-with-three-headers-related-to-each-data-cell)의
다단계 표와 동일한 정보를 제공한다.
따라서 누구나 정보를 더 쉽게 이해하고 코드를 작성하기 쉽다.
또한 간단한 표는 WYSIWYG 편집기를 비롯한 웹 콘텐츠 작성 도구에서 훨씬 더 잘 지원된다.

#### 예제

<div class="box-i">
<p><strong>Availability of holiday accommodation</strong></p>
<table class="numbers" summary="Column one has the location and size of accommodation, other columns show the type and number of properties available">
<caption>
    Paris
</caption>
<thead>
    <tr>
        <td></td>
        <th scope="col">
            Studio
        </th>
        <th scope="col">
            <abbr title="Apartment">Apt</abbr>
        </th>
        <th scope="col">
            Chalet
        </th>
        <th scope="col">
            Villa
        </th>
    </tr>
</thead>
<tbody>
    <tr>
        <th scope="row">
            1 bedroom
        </th>
        <td>
            11
        </td>
        <td>
            20
        </td>
        <td>
            25
        </td>
        <td>
            23
        </td>
    </tr>
    <tr>
        <th scope="row">
            2 bedroom
        </th>
        <td>
            -
        </td>
        <td>
            43
        </td>
        <td>
            52
        </td>
        <td>
            32
        </td>
    </tr>
    <tr>
        <th scope="row">
            3 bedroom
        </th>
        <td>
            -
        </td>
        <td>
            13
        </td>
        <td>
            15
        </td>
        <td>
            40
        </td>
    </tr>
  </tbody>
</table>
<table class="numbers" style="margin-top:1em;">
<caption>
    Rome
</caption>
<thead>
    <tr>
        <td></td>
        <th scope="col">
            Studio
        </th>
        <th scope="col">
            <abbr title="Apartment">Apt</abbr>
        </th>
        <th scope="col">
            Chalet
        </th>
        <th scope="col">
            Villa
        </th>
    </tr>
</thead>
<tbody>
    <tr>
        <th id="rbed1">
            1 bedroom
        </th>
        <td>
            13
        </td>
        <td>
            21
        </td>
        <td>
            22
        </td>
        <td>
            3
        </td>
    </tr>
    <tr>
        <th id="rbed2">
            2 bedroom
        </th>
        <td>
            -
        </td>
        <td>
            23
        </td>
        <td>
            43
        </td>
        <td>
            30
        </td>
    </tr>
    <tr>
        <th id="rbed3">
            3 bedroom
        </th>
        <td>
            -
        </td>
        <td>
            16
        </td>
        <td>
            32
        </td>
        <td>
            40
        </td>
    </tr>
</tbody>
</table>

</div>

## [캡션 및 요약](https://www.w3.org/WAI/tutorials/tables/caption-summary/)

캡션과 요약은 사용자가 표를 찾고, 탐색하고, 이해하는 데 도움이 되는 정보를 제공한다.
모든 경우에 캡션과 요약이 WCAG를 준수해야 하는 것은 아니지만, 캡션과 요약은 종종 필요한 정보를 제공하는 매우 간단한 방법이다.

- **캡션**은 표의 제목과 같은 기능을 한다.
  대부분의 스크린 리더는 캡션의 내용을 알려준다.
  캡션은 사용자가 표를 찾고 표의 내용을 이해하여 읽을지 여부를 결정하는 데 도움이 된다.
  사용자가 "표 모드"를 사용하는 경우 캡션은 표를 식별하는 기본 메커니즘이다.
  캡션은 `<caption>` 요소로 제공된다.

- **요약**은 표의 데이터 구성에 대한 정보를 전달하고 사용자가 표를 탐색하는 데 도움을 준다.
  예를 들어, 아래 예제에서처럼 표의 구조가 비정상적인 경우 어떤 행이나 열에서 어떤 콘텐츠를 찾을 수 있는지에 대한 정보를 사용자에게 제공할 수 있다.
  요약은 일반적으로 복잡한 표에만 필요하다.

하나의 표에 캡션과 요약이 모두 제공되는 경우 요약은 캡션에 있는 정보와 중복되지 않아야 한다.

WCAG 기술 [H39: 캡션 요소를 사용하여 데이터 표 캡션을 데이터 표과 연결하기](https://www.w3.org/WAI/WCAG21/Techniques/html/H39)에서 캡션에 대한 자세한 내용을 볼 수
있다.

### [캡션을 사용하여 표 식별하기](https://www.w3.org/WAI/tutorials/tables/caption-summary/#identifying-a-table-using-a-caption)

캡션은 표 콘텐츠에 대한 짧은 제목이어야 한다.
이 예제에서 "Concerts"는 사용자에게 표에 어떤 정보가 있는지 알려준다(예: 표에 미술 전시회 정보도 포함될 수 있음).

`<caption>` 요소는 `<table>` 요소의 하위 요소로 직접 배치된다.

#### 예제

<table>
  <caption>Concerts</caption>
  <tbody><tr>
    <th>Date</th>
    <th>Event</th>
    <th>Venue</th>
  </tr>
  <tr>
    <td>12 Feb</td>
    <td>Waltz with Strauss</td>
    <td>Main Hall</td>
  </tr>
  <tr>
    <td>24 Mar</td>
    <td>The Obelisks</td>
    <td>West Wing</td>
  </tr>
  <tr>
    <td>14 Apr</td>
    <td>The What</td>
    <td>Main Hall</td>
  </tr>
</tbody></table>

#### 코드 스니펫

```html
<table>
  <caption>
    Concerts
  </caption>
  <tr>
    <th>Date</th>
    <th>Event</th>
    <th>Venue</th>
  </tr>
  <tr>
    <td>12 Feb</td>
    <td>Waltz with Strauss</td>
    <td>Main Hall</td>
  </tr>
  […]
</table>
```

### [더 복잡한 표를 위한 요약](https://www.w3.org/WAI/tutorials/tables/caption-summary/#summaries-for-more-complex-tables)

아래 예제에서는 사용자에게 요약을 제공하기 위해 다양한 기법이 사용된다.

#### [방법 1: `<caption>` 요소 안에 요약 중첩](https://www.w3.org/WAI/tutorials/tables/caption-summary/#nesting-summary-inside-the-caption-element)

이 복잡한 표는 두 개의 개별 위치에서 다양한 유형과 크기의 숙박시설의 이용 가능 여부를 보여준다.
`<caption>` 요소는 표의 제목 역할을 하며 표의 구성을 설명하는 요약도 제공한다.

이 방식으로 구현하면 시각적 사용자도 요약을 사용할 수 있다.

##### 예제

<table>
  <caption style="text-align: left;">
    Availability of holiday accommodation<br>
    <span style="font-size: .75em; display:block;">
      Column one has the location and size of accommodation, other columns show the type and number of properties available
    </span>
  </caption>
  <thead>
    <tr>
      <td></td>
      <th id="stud" scope="col"> Studio </th>
      <th id="apt" scope="col"> <abbr title="Apartment">Apt</abbr> </th>
      <th id="chal" scope="col"> Chalet </th>
      <th id="villa" scope="col"> Villa </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th id="par" class="span" colspan="5" scope="colgroup"> Paris </th>
    </tr>
    <tr>
      <th headers="par" id="pbed1"> 1 bedroom </th>
      <td headers="par pbed1 stud"> 11 </td>
      <td headers="par pbed1 apt"> 20 </td>
      <td headers="par pbed1 chal"> 25 </td>
      <td headers="par pbed1 villa"> 23 </td>
    </tr>
    <tr>
      <th headers="par" id="pbed2"> 2 bedroom </th>
      <td headers="par pbed2 stud"> - </td>
      <td headers="par pbed2 apt"> 43 </td>
      <td headers="par pbed2 chal"> 52 </td>
      <td headers="par pbed2 villa"> 32 </td>
    </tr>
    <tr>
      <th headers="par" id="pbed3"> 3 bedroom </th>
      <td headers="par pbed3 stud"> - </td>
      <td headers="par pbed3 apt"> 13 </td>
      <td headers="par pbed3 chal"> 15 </td>
      <td headers="par pbed3 villa"> 40 </td>
    </tr>
    <tr>
      <th id="rome" class="span" colspan="5" scope="colgroup"> Rome </th>
    </tr>
    <tr>
      <th id="rbed1" headers="rome"> 1 bedroom </th>
      <td headers="rome rbed1 stud"> 13 </td>
      <td headers="rome rbed1 apt"> 21 </td>
      <td headers="rome rbed1 chal"> 22 </td>
      <td headers="rome rbed1 villa"> 3 </td>
    </tr>
    <tr>
      <th id="rbed2" headers="rome"> 2 bedroom </th>
      <td headers="rome rbed2 stud"> - </td>
      <td headers="rome rbed2 apt"> 23 </td>
      <td headers="rome rbed2 chal"> 43 </td>
      <td headers="rome rbed2 villa"> 30 </td>
    </tr>
    <tr>
      <th id="rbed3" headers="rome"> 3 bedroom </th>
      <td headers="rome rbed3 stud"> - </td>
      <td headers="rome rbed3 apt"> 16 </td>
      <td headers="rome rbed3 chal"> 32 </td>
      <td headers="rome rbed3 villa"> 40 </td>
    </tr>
  </tbody>
</table>

##### 코드 스니펫

```html
<caption>
  Availability of holiday accommodation
  <br />
  <span
    >Column one has the location and size of accommodation, other columns show
    the type and number of properties available</span
  >
</caption>
```

> 참고
>
> 요약의 스타일을 캡션과 다르게 지정하기 위해 `span` 요소가 추가되었다.
> 이 요소는 필수는 아니다.

#### [방법 2: `aria-describedby`으로 표 요약 제공](https://www.w3.org/WAI/tutorials/tables/caption-summary/#using-aria-describedby-to-provide-a-table-summary)

이 접근 방식에서는 `id` 속성이 있는 요소는 표의 `aria-describedby` 속성을 사용하여 요약과 연결된다.
고유한 `id` 속성이 있는 모든 요소는 이러한 방식으로 표의 요약으로 사용할 수 있다.

요약이 포함된 요소가 문서의 표 앞에 있을 필요는 없지만, 특히 스크린 리더를 사용하지 않는 경우 요약이 표 근처에 있으면 사용자가 요약을 더 빨리 찾을 수 있다.

> 참고
>
> 이 WAI-ARIA 기능은 이 페이지의 요약에 대한 다른 접근 방식에 비해 보조 기술에서 널리 지원되지 않을 수 있다.

##### 예제

<div class="box-i">

<p id="tblDesc" style="max-width: 25.333333333em; font-size: .75em; lin-height: 1.5;">Column one has the location and size of accommodation, other columns show the type and number of properties available.</p>
<table aria-describedby="tblDesc" tabindex="0">
  <caption style="text-align: left;">
    Paris: Availability of holiday accommodation<br>
  </caption>
  <thead>
    <tr>
      <td></td>
      <th id="stud" scope="col"> Studio </th>
      <th id="apt" scope="col"> <abbr title="Apartment">Apt</abbr> </th>
      <th id="chal" scope="col"> Chalet </th>
      <th id="villa" scope="col"> Villa </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th headers="par" id="pbed1"> 1 bedroom </th>
      <td headers="par pbed1 stud"> 11 </td>
      <td headers="par pbed1 apt"> 20 </td>
      <td headers="par pbed1 chal"> 25 </td>
      <td headers="par pbed1 villa"> 23 </td>
    </tr>
    <tr>
      <th headers="par" id="pbed2"> 2 bedroom </th>
      <td headers="par pbed2 stud"> - </td>
      <td headers="par pbed2 apt"> 43 </td>
      <td headers="par pbed2 chal"> 52 </td>
      <td headers="par pbed2 villa"> 32 </td>
    </tr>
    <tr>
      <th headers="par" id="pbed3"> 3 bedroom </th>
      <td headers="par pbed3 stud"> - </td>
      <td headers="par pbed3 apt"> 13 </td>
      <td headers="par pbed3 chal"> 15 </td>
      <td headers="par pbed3 villa"> 40 </td>
    </tr>
  </tbody>
</table>

</div>

##### 코드 스니펫

```html
<p id="tblDesc">
  Column one has the location and size of accommodation, other columns show the
  type and number of properties available.
</p>
<table aria-describedby="tblDesc">
  […]
</table>
```

#### [방법 3: `<figure>` 요소를 사용하여 표 요약 마크업](https://www.w3.org/WAI/tutorials/tables/caption-summary/#using-the-figure-element-to-mark-up-a-table-summary)

이 접근 방식에서는 표를 `<figure>` 요소로 감싼다.
`<figcaption>` 요소에는 캡션과 요약 텍스트가 포함된다.

"표 모드"로 탐색하는 스크린 리더 사용자는 일반적으로 이렇게 적용된 캡션으로는 표를 식별할 수 없다.
`<figcaption>` 요소의 캡션 부분은 `aria-labelledby` 속성을 사용하여 표에 명시적으로 연결할 수 있고 요약 부분은 `aria-describedby` 속성을 사용하여 표에 연결할 수 있다.
이렇게 하면 캡션과 요약이 여러 번 읽힐 수 있다.

> 참고
>
> 이 HTML5 기능은 이 페이지의 요약에 대한 다른 접근 방식보다 보조 기술에서 널리 지원되지 않을 수 있다.

##### 예제

<figure>
  <figcaption style="max-width: 19em; color: inherit;">
    <strong>Paris: Availability of holiday accommodation</strong><br>Column one has the location and size of accommodation, other columns show the type and number of properties available.
  </figcaption>
  <table>
    <thead>
      <tr>
        <td></td>
        <th id="stud" scope="col"> Studio </th>
        <th id="apt" scope="col"> <abbr title="Apartment">Apt</abbr> </th>
        <th id="chal" scope="col"> Chalet </th>
        <th id="villa" scope="col"> Villa </th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th headers="par" id="pbed1"> 1 bedroom </th>
        <td headers="par pbed1 stud"> 11 </td>
        <td headers="par pbed1 apt"> 20 </td>
        <td headers="par pbed1 chal"> 25 </td>
        <td headers="par pbed1 villa"> 23 </td>
      </tr>
      <tr>
        <th headers="par" id="pbed2"> 2 bedroom </th>
        <td headers="par pbed2 stud"> - </td>
        <td headers="par pbed2 apt"> 43 </td>
        <td headers="par pbed2 chal"> 52 </td>
        <td headers="par pbed2 villa"> 32 </td>
      </tr>
      <tr>
        <th headers="par" id="pbed3"> 3 bedroom </th>
        <td headers="par pbed3 stud"> - </td>
        <td headers="par pbed3 apt"> 13 </td>
        <td headers="par pbed3 chal"> 15 </td>
        <td headers="par pbed3 villa"> 40 </td>
      </tr>
    </tbody>
  </table>
</figure>

##### 코드 스니펫: WAI-ARIA 사용 안 함

```html
<figure>
  <figcaption>
    <strong>Paris: Availability of holiday accommodation</strong><br />
    <span
      >Column one has the location and size of accommodation, other columns show
      the type and number of properties available.</span
    >
  </figcaption>
  <table>
    […]
  </table>
</figure>
```

##### 코드 스니펫: WAI-ARIA 사용

```html
<figure>
  <figcaption>
    <strong id="paris-caption"
      >Paris: Availability of holiday accommodation</strong
    ><br />
    <span id="paris-summary"
      >Column one has the location and size of accommodation, other columns show
      the type and number of properties available.</span
    >
  </figcaption>
  <table aria-labelledby="paris-caption" aria-describedby="paris-summary">
    […]
  </table>
</figure>
```

## [팁과 요령](https://www.w3.org/WAI/tutorials/tables/tips/)

- **단순하게 유지하라**: 복잡한 표는 콘텐츠 제작자에게는 더 많은 작업을 요구하고 사용자에게는 해석하기 더 어렵다.
  일반적으로 복잡한 표를 하나의 하위 주제에 대한 데이터를 포함하는 간단한 개별 표로 나누는 것이 좋다.

- **반응형 디자인**: 작은 화면, 작은 뷰포트, 확대된 뷰, 확대된 텍스트 등의 상황에서는 반응형 표의 형식이 변경되는 경우가 많다.
  구조 관계를 모든 형식에서 사용할 수 있는지 확인해야 한다.

- **표 분리**: 여러 표가 서로 이어지는 경우 하나의 표를 사용하지 말고 `<th>` 셀을 추가 행에 넣어야 한다.
  스크린 리더는 한 열의 모든 `<th>` 셀을 소리내어 읽을 수 있으므로 혼동을 일으킬 수 있다.
  [주제가 변경되면 새 `<table>`을 시작하라.](https://www.w3.org/WAI/tutorials/tables/multi-level/#split-up-multi-level-tables)

- **데이터 분리**

  - 각 개별 데이터에 해당하는 셀이 있는지 확인하라.
    한 열에는 헤더를, 다른 열에는 모든 데이터를 사용하면 스크린 리더가 열 간 데이터 관계를 파악하는 것이 거의 불가능하므로 사용하면 안 된다.

    ![On the left, a table with two columns is shown. The header for the first column reads “Shirt” and the header for the second column reads “Sizes and amount in stock”. The second row reads “Blue” in the first column and “S: 6; M: 13, XL: 10”. In the second row, Sizes for a “Red” shirt are “M: 2; L: 9; XL: 10; XXL: 1”. On the right, the table is split up in “Shirt”, “Size” and “Stock” columns.](https://www.w3.org/WAI/content-images/tutorials/tables/headers-in-one-column-all-data-in-second.png)

  - 텍스트 크기를 조절할 때 의사 행의 데이터가 더 이상 올바르게 정렬되지 않을 수 있으므로 표 행을 만들 때 줄 바꿈(`<br>` 요소)을 사용하면 안 된다.

    ![On the top there is a table where the content and header cells are not marked up correctly. Line breaks are used to make items look like they align correctly. When resizing the text (bottom) the items don’t line up anymore](https://www.w3.org/WAI/content-images/tutorials/tables/table-text-resize.png)

- **정렬**: 텍스트는 왼쪽에, 숫자 데이터는 오른쪽에 정렬하면(왼쪽에서 오른쪽 언어 기준) 텍스트 크기가 크거나 화면이 작은 사용자도 쉽게 찾을 수 있다.
  이 기능은 셀이 두 개 이상의 열에 걸쳐 있는 경우에 특히 유용하다.
  열 헤더의 정렬을 아래 셀의 데이터와 동일하게 지정하면 도움이 된다.

- **헤더 셀 스타일 지정**: `<th>` 요소는 헤더 셀에 사용되며, 다른 스타일로 `<td>` 요소를 사용하면 표에 접근할 수는 있지만 접근성이 떨어진다.
  또한 `<th>`와 `<td>` 셀을 시각적으로 구분하는 것이 도움이 된다.
  예를 들어 이 튜토리얼 페이지에서 헤더 셀은 짙은 회색 배경을 사용한다.

- **얼룩말 표**: 짝수 행과 홀수 행을 다른 방식으로 스타일링하면 읽기에 어려움이 있거나 텍스트를 확대해서 보는 사람들에게 도움이 될 수 있다.
  이 스타일링은 시각적 가이드 역할을 한다.
  마우스오버 및 키보드 포커스 시 셀(및 행/열)을 강조 표시하여 사람들이 현재 위치를 확인할 수 있도록 지원한다.
  헤더와 데이터 셀 모두에서 텍스트와 배경의 대비 비율이 적절한지 확인해야 한다.
  [색상 대비 비율을 확인하는 방법은 링크를 참조.](https://www.w3.org/WAI/test-evaluate/preliminary/#contrast)

- **유연성**: 표의 레이아웃 모델 때문에 작은 화면에서는 표가 작게 보이지 않거나 사용자가 확대할 때 너무 넓어지는 경우가 있다.
  이러한 상황에서는 표가 잘리지 않도록 하는 것이 중요하다(예: CSS에서 `overflow: hidden` 사용).
  이 튜토리얼에서는 사용자가 표를 가로로 스크롤할 수 있도록 표를 감싸는 요소에 `overflow: scroll`을 적용했지만 이러한 상황에서 표를 표시하는 데는 훨씬 더 많은 옵션이 있다.

- **레이아웃용 표**: 표는 레이아웃 용도로 사용해서는 안 된다.
  레이아웃에는 CSS를 사용해야 한다.
  이미 레이아웃용 표가 있는 경우 이 튜토리얼에서 설명하는 구조 요소(예: `<th>` 또는 `<caption>`)와 속성을 사용하지 말고 `<table>` 요소에 `role="presentation"`을
  추가하라.

### 기타 W3C 리소스

- "장애인이 웹을 사용하는 방법"에서 접근성
  원칙의 [콘텐츠는 다양한 방식으로 표시될 수 있다](https://www.w3.org/WAI/fundamentals/accessibility-principles/#adaptable) 섹션
