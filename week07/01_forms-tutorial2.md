양식 => 폼
확인란 => 체크박스
화면 리더
니다.
세요.

# [폼 튜토리얼](https://www.w3.org/WAI/tutorials/forms/)

폼은 웹사이트와 웹 애플리케이션에서 사용자 상호 작용을 제공하는 데 일반적으로 사용한다.
예를 들어 로그인, 등록, 댓글 작성, 구매 등이 이에 해당한다.
이 튜토리얼에서는 접근성 있는 폼을 만드는 방법을 보여준다.
처리되는 폼이 클라이언트 측이든 서버 측이든 모든 폼에 동일한 개념이 적용된다.

기술적 고려 사항 외에도 사용자는 일반적으로 간단하고 짧은 폼을 선호한다.
사용자에게 거래 또는 프로세스를 완료하는 데 필요한 정보만 입력하도록 요청하는 게 좋다.
관련성이 없거나 과도한 데이터를 요청하면 사용자가 폼을 포기할 가능성이 높다.

- **[Labeling Controls](https://www.w3.org/WAI/tutorials/forms/labels/):** Use the `<label>` element, and, in specific cases, other mechanisms (e.g. WAI-ARIA, `title` attribute etc.), to identify each form control.
- **[Grouping Controls](https://www.w3.org/WAI/tutorials/forms/grouping/):** Use the `<fieldset>` and `<legend>` elements to group and associate related form controls.
- **[Form Instructions](https://www.w3.org/WAI/tutorials/forms/instructions/):** Provide instructions to help users understand how to complete the form and individual form controls.
- **[Validating Input](https://www.w3.org/WAI/tutorials/forms/validation/):** Validate input provided by the user and provide options to undo changes and confirm data entry.
- **[User Notifications](https://www.w3.org/WAI/tutorials/forms/notifications/):** Notify users about successful task completion, any errors, and provide instructions to help them correct mistakes.
- **[Multi-Page Forms](https://www.w3.org/WAI/tutorials/forms/multi-page/):** Divide long forms into multiple smaller forms that constitute a series of logical steps or stages and inform users about their progress.
- **[Custom Controls](https://www.w3.org/WAI/tutorials/forms/custom-controls/):** Use stylized form elements and other progressive enhancement techniques to provide custom controls.

## 시간 제한에 대한 참고 사항

가능하면 사용자가 자신의 속도에 맞춰 폼을 작성할 수 있도록 양식에 시간 제한을 두지 않아야 한다.
예를 들어 보안상의 이유로 시간 제한이 필요한 경우에는 사용자가 시간 제한을 끄거나 연장할 수 있는 옵션이 있어야 한다.
시간 제한이 경매나 게임과 같은 실시간 이벤트로 인한 것이거나 유효한 제출을 위해 폼을 작성하는 데 시간이 필수적인 경우에는 이 제한이 적용되지 않는다.

## 폼, 왜 중요할까?

양식은 시각적으로나 인지적으로 복잡하고 사용하기 어려울 수 있다.
접근성 있는 양식은 장애인을 포함한 모든 사람이 더 쉽게 사용할 수 있다.

- 양식에 접근성을 높이면 레이아웃 구조, 지침 및 피드백이 개선되므로 **인지 장애가 있는 사람**은 양식과 양식 작성 방법을 더 잘 이해할 수 있다.
- **음성 입력 사용자**는 음성 명령을 통해 레이블을 사용하여 컨트롤을 활성화하고 완료해야 하는 필드로 초점을 이동할 수 있다.
- **손재주가 부족한 사람**은 특히 라디오 버튼이나 체크박스와 같은 작은 컨트롤의 경우 레이블을 포함한 클릭 가능한 영역이 큰 것이 유리하다.
- **스크린 리더 사용자**는 양식 컨트롤이 레이블, 필드 세트 및 기타 구조적 요소와 연결되어 있기 때문에 더 쉽게 식별하고 이해할 수 있다.

## [컨트롤에 레이블 지정하기](https://www.w3.org/WAI/tutorials/forms/labels/)

텍스트 필드, 확인란, 라디오 버튼, 드롭다운 메뉴 등 모든 양식 컨트롤을 식별하는 레이블을 제공합니다.
대부분의 경우 `<label>` 요소를 사용하여 이 작업을 수행합니다.

레이블은 양식 컨트롤의 목적을 설명해야 합니다.
이 튜토리얼의 이 섹션에서는 양식 컨트롤과 올바르게 연결된 레이블을 제공하는 방법을 설명합니다.
이후 섹션에서는 사용자가 양식을 작성할 수 있도록 [지침](https://www.w3.org/WAI/tutorials/forms/instructions), [사용자 입력 확인](https://www.w3.org/WAI/tutorials/forms/validation) 및 [피드백 제공](https://www.w3.org/WAI/tutorials/forms/notifications)을 제공하는 방법에 대해 설명합니다.

레이블과 양식 컨트롤은 암시적으로 또는 명시적으로 서로 연결되어 있어야 합니다.
예를 들어 웹 브라우저는 컨트롤을 선택하거나 활성화하기 위해 레이블을 제공해서 클릭 가능한 영역을 더 크게 만든다.
또한 보조 기술이 양식 컨트롤을 표시할 때 올바른 레이블을 참조할 수 있도록 보장합니다.

### [명시적으로 레이블 연결하기](https://www.w3.org/WAI/tutorials/forms/labels/#associating-labels-explicitly)

가능하면 `label` 요소를 사용하여 텍스트를 양식 요소와 명시적으로 연결해야 한다.
레이블의 `for` 속성은 양식 컨트롤의 `id`와 정확히 일치해야 합니다.

###### 예제

<label for="firstname">First name:</label>
<input type="text" name="firstname" id="firstname"><br>

<input type="checkbox" name="subscribe" id="subscribe">
<label for="subscribe">Subscribe to newsletter</label>

###### 코드 스니펫

```
<label for="firstname">First name:</label>
<input type="text" name="firstname" id="firstname"><br>

<input type="checkbox" name="subscribe" id="subscribe">
<label for="subscribe">Subscribe to newsletter</label>
```

#### [레이블 텍스트 숨기기](https://www.w3.org/WAI/tutorials/forms/labels/#hiding-label-text)

양식 컨트롤의 레이블은 모든 사람이 그 목적을 더 잘 이해할 수 있도록 도와줍니다.
어떤 경우에는 콘텐츠가 시각적으로 렌더링될 때 컨텍스트에서 목적이 충분히 명확할 수 있습니다.
레이블은 시각적으로 숨길 수 있지만 화면 리더 및 음성 입력 사용자와 같은 다른 형태의 표시 및 상호 작용을 지원하려면 여전히 코드 내에 제공해야 합니다.
이 튜토리얼에서 시각적으로 요소를 숨기되 보조 기술에서 사용할 수 있도록 하는 방법은 [요소 숨기기 관련 참고 사항](https://www.w3.org/WAI/tutorials/forms/labels/#note-on-hiding-elements)에 설명되어 있습니다.

아래 예시에서는 검색 버튼 바로 옆에 검색 필드가 배치되어 있습니다.
텍스트 입력 필드의 용도는 대부분의 상황에서 문맥을 통해 명확하게 알 수 있습니다.

###### 예제

<form method="post" action="#">
  <style>
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
  <div>
    <label for="search" class="visuallyhidden">Search: </label>
    <input type="text" name="search" id="search">
    <button type="button">Search</button>
  </div>
</form>

##### [레이블 요소 숨기기](https://www.w3.org/WAI/tutorials/forms/labels/#hiding-the-label-element)

이 접근 방식에서는 코드 내에서 양식 컨트롤을 식별하기 위해 `<label>` 요소를 제공하지만 시각적 단서를 통해 목적을 추론할 수 있는 사용자의 경우 중복을 피하기 위해 시각적으로 숨겨져 있습니다.

###### 코드 스니펫

```
<label for="search" class="visuallyhidden">Search: </label>
<input type="text" name="search" id="search">
<button type="submit">Search</button>
```

##### [`aria-label` 사용하기](https://www.w3.org/WAI/tutorials/forms/labels/#using-aria-label)

`aria-label` 속성은 양식 컨트롤을 식별하는 데에도 사용할 수 있습니다.
이 접근 방식은 스크린 리더 및 기타 보조 기술에서 잘 지원하지만, `title` 속성(아래 참조)과 달리 시각적 사용자에게 정보가 전달되지 않습니다.
따라서 이 접근 방식은 아래 예시의 버튼처럼 컨트롤의 레이블이 주변 콘텐츠에서 명확하게 구분되는 경우에만 사용해야 합니다.

###### 코드 스니펫

```
<input type="text" name="search" aria-label="Search">
<button type="submit">Search</button>
```

##### [`aria-labelledby` 사용하기](https://www.w3.org/WAI/tutorials/forms/labels/#using-aria-labelledby)

`aria-labelledby` 속성은 양식 컨트롤을 식별하는 데에도 사용할 수 있습니다.
이 접근 방식은 스크린 리더 및 기타 보조 기술에서 잘 지원되지만, `title` 속성(아래 참조)과 달리 시각적 사용자에게 정보가 전달되지 않습니다.
따라서 이 접근 방식은 아래 예시의 버튼처럼 컨트롤의 레이블이 주변 콘텐츠에서 명확하게 구분되는 경우에만 사용해야 합니다.

레이블 텍스트가 포함된 요소의 `id`는 `aria-labelledby` 속성의 값으로 사용한다.

###### 코드 스니펫

```
<input type="text" name="search" aria-labelledby="searchbutton">
<button id="searchbutton" type="submit">Search</button>
```

##### [`title` 속성 사용하기](https://www.w3.org/WAI/tutorials/forms/labels/#using-the-title-attribute)

`title` 속성은 양식 컨트롤을 식별하는 데에도 사용할 수 있습니다.
일부 화면 리더 및 보조 기술은 `title` 속성을 레이블 요소를 대체하는 것으로 해석하지 않기 때문에 일반적으로 이 접근 방식은 신뢰성이 떨어지고 권장되지 않으며, `title` 속성이 필수가 아닌 정보를 제공하는 데 자주 사용되기 때문일 수 있습니다.
`title` 속성의 정보는 마우스로 양식 필드를 가리키면 시각적 사용자에게 도구 팁으로 표시한다.

###### 예제

<input title="Search" type="text" name="search">
<button type="submit">Search</button>

###### 코드 스니펫

```
<input title="Search" type="text" name="search">
<button type="submit">Search</button>
```

##### [요소 숨기기 관련 참고 사항](https://www.w3.org/WAI/tutorials/forms/labels/#note-on-hiding-elements)

스크린 리더 및 기타 보조 기술은 웹 브라우저와 마찬가지로 `display: none;` 및 `visibility: hidden;`을 사용하여 스타일을 지정할 때 사용자에게 요소를 숨깁니다.

정보를 시각적으로 숨기되 화면 리더 및 기타 보조 기술 사용자가 계속 사용할 수 있도록 하는 데 사용되는 일반적인 접근 방식은 정보를 기술적으로는 표시하지만 실질적으로는 숨기는 CSS를 사용하는 것입니다.
예를 들어, 아래의 CSS 클래스 `visuallyhidden`(`visibility: hidden` CSS와 **혼동하면 안 된다.**)와 같이 1x1 픽셀 영역에 레이블을 표시하는 것이 그 예입니다:

###### 코드 스니펫

```
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
```

이 코드를 사용할 때 대화형 요소는 여전히 활성화되어 있으므로 레이블을 제외한 양식의 다른 부분을 숨기는 것은 적합하지 않습니다.

### [암시적으로 레이블 연결하기](https://www.w3.org/WAI/tutorials/forms/labels/#associating-labels-implicitly)

일부 상황에서는 양식 컨트롤에 명시적으로 레이블을 지정할 수 없습니다.
예를 들어 콘텐츠 작성자가 스크립트에서 생성된 양식 필드의 `id`를 모르거나 해당 스크립트가 `id`를 전혀 추가하지 않을 수 있습니다.
이 경우 `label` 요소는 양식 컨트롤과 레이블 텍스트의 컨테이너로 사용되므로 두 요소가 암시적으로 연결됩니다.
일반적으로 명시적 레이블은 보조 기술에서 더 잘 지원됩니다.

###### 코드 스니펫

```
<label>
  First name:
  <input type="text" name="firstname">
</label>
<br>
<label>
  <input type="checkbox" name="subscribe">
  Subscribe to newsletter
</label>
```

### [버튼에 레이블 지정하기](https://www.w3.org/WAI/tutorials/forms/labels/#labeling-buttons)

`<button>` 요소의 레이블은 요소 내부에 설정되며 마크업을 포함할 수 있습니다.
이를 통해 언어 변경 마크업과 같이 더 나은 접근성 힌트를 포함할 수 있습니다.
`<input>` 요소를 사용하여 버튼을 만들 때 레이블은 요소의 `value` 속성에 설정됩니다.

```
<button type="submit">Submit</button>
<button type="button">Cancel</button>

<input type="submit" value="Submit">
<input type="button" value="Cancel">
```

> 참고
>
> 이미지 버튼(`<input type="image">`)을 사용하는 경우 `<input type="image" src="searchbutton.png" alt="Search">`와 같이 `alt` 속성에 레이블이 설정됩니다.
> 버튼에 있는 이미지를 설명하는 방법에 대한 자세한 내용은 [기능적 이미지](https://www.w3.org/WAI/tutorials/images/functional/#image-used-in-a-button)를 참조하세요.

### [레이블 텍스트의 시각적 위치](https://www.w3.org/WAI/tutorials/forms/labels/#visual-position-of-label-text)

왼쪽에서 오른쪽으로 쓰는 언어에서는 레이블을 라디오 버튼과 확인란의 오른쪽, 다른 양식 필드의 왼쪽 또는 바로 위에 시각적으로 배치하는 것이 일반적입니다.
이 원칙을 유지하면 모든 사용자가 양식을 더 잘 예측하고 이해할 수 있습니다.

일반적으로 양식 필드 위에 레이블을 배치하면 저시력자 및 모바일 장치 사용자의 가로 스크롤을 줄이는 데 도움이 됩니다.
그러나 이 접근 방식의 유용성은 주변의 다른 양식 필드 및 콘텐츠의 근접성 등 다른 디자인 측면에 따라 달라지므로 개별적으로 평가해야 합니다.
목표는 레이블과 양식 컨트롤 사이에 밀접하고 뚜렷한 시각적 관계를 유지하는 것입니다.

### [모바일용 양식 필드 컨트롤](https://www.w3.org/WAI/tutorials/forms/labels/#form-field-controls-for-mobile)

HTML5 양식 필드를 사용하면 가상 키보드가 표시되어 데이터를 더 쉽게 입력할 수 있습니다.
예를 들어 '숫자' 필드에는 숫자 키보드가, '날짜' 필드에는 기본 날짜 선택기가 표시됩니다.

간혹 디자이너가 눈에 보이는 레이블을 포함하지 않을 것을 제안하기도 합니다.
하지만 대부분의 사용자는 양식을 이해하기 위해 눈에 보이는 레이블을 선호하거나 심지어 필요하기도 합니다.

## [컨트롤 그룹화](https://www.w3.org/WAI/tutorials/forms/grouping/)

연관된 양식 컨트롤을 그룹화하면 연관된 컨트롤을 더 쉽게 식별할 수 있으므로 모든 사용자가 양식을 더 쉽게 이해할 수 있습니다.
또한 사람들이 전체 양식을 한 번에 파악하기보다는 관리하기 쉬운 작은 그룹에 집중할 수 있습니다.

그룹화는 시각적으로 그리고 코드에서 수행해야 합니다(예: `<fieldset>` 및 `<legend>` 요소를 사용하여 관련 양식 컨트롤을 연결).
또한 `<select>` 요소의 관련 항목은 `<optgroup>`을 사용하여 그룹화할 수 있습니다.

### [연관된 컨트롤을 `fieldset`로 연결하기](https://www.w3.org/WAI/tutorials/forms/grouping/#associating-related-controls-with-fieldset)

`<fieldset>` 요소는 관련 양식 컨트롤을 위한 컨테이너를 제공하고 `<legend>` 요소는 그룹을 식별하는 제목 역할을 합니다.

컨트롤 그룹에 대한 범례는 모든 컨트롤의 공통 속성을 강조 표시하여 그룹의 모든 필드가 필수임을 알릴 수도 있습니다.

#### [라디오 버튼](https://www.w3.org/WAI/tutorials/forms/grouping/#radio-buttons)

아래 예제에는 사용자가 출력 형식을 선택할 수 있는 세 개의 라디오 버튼이 있습니다.
라디오 버튼 그룹은 항상 `<fieldset>`을 사용하여 그룹화해야 합니다.

###### 예제

<form method="post" action="#">
<fieldset style="border: 1px solid #888; padding: 5px;">
<legend>Output format</legend>
  <div>
    <input type="radio" name="format" id="txt" value="txt" checked=""> <label for="txt">Text file</label>
  </div>
  <div>
    <input type="radio" name="format" id="csv" value="csv"> <label for="csv">CSV file</label>
  </div>
  <div>
    <input type="radio" name="format" id="html" value="HTML"> <label for="html">HTML file</label>
  </div>
</fieldset>
</form>

###### 코드 스니펫

```
<fieldset>
<legend>Output format</legend>
  <div>
    <input type="radio" name="format" id="txt" value="txt" checked>
    <label for="txt">Text file</label>
  </div>
  <div>
    <input type="radio" name="format" id="csv" value="csv">
    <label for="csv">CSV file</label>
  </div>
  […]
</fieldset>
```

#### [체크박스](https://www.w3.org/WAI/tutorials/forms/grouping/#checkboxes)

아래 예제에서 세 개의 확인란은 다양한 유형의 정보를 수신하기 위한 옵트인 기능의 일부입니다.

###### 예제

<form method="post" action="#">
<fieldset style="border: 1px solid #888; padding: 5px;">
<legend>I want to receive</legend>
	<div>
		<input type="checkbox" name="newsletter" id="check_1"> <label for="check_1">The weekly newsletter</label>
	</div>
	<div>
		<input type="checkbox" name="company_offers" id="check_2"> <label for="check_2">Offers from the company</label>
	</div>
	<div>
		<input type="checkbox" name="assoc_offers" id="check_3"> <label for="check_3">Offers from associated companies</label>
	</div>
</fieldset>
</form>

###### 코드 스니펫

```
<fieldset>
<legend>I want to receive</legend>
	<div>
		<input type="checkbox" name="newsletter" id="check_1">
    <label for="check_1">The weekly newsletter</label>
	</div>
	[…]
</fieldset>
```

#### [연관된 필드](https://www.w3.org/WAI/tutorials/forms/grouping/#related-fields)

이 예제에서는 배송 및 청구 주소를 입력하는 양식 필드를 보여줍니다.
두 그룹의 레이블에는 동일한 텍스트가 있으므로 `fieldset` 요소는 그룹별로 양식 필드를 구분하는 데 도움이 됩니다.
화면 리더에서 `<legend>`를 읽을 수 없는 경우(아래 참고를 참조) 각 그룹의 첫 번째 양식 컨트롤의 레이블에는 그룹 이름이 포함되어야 합니다.
이 이름은 시각적으로 숨길 수 있습니다.

###### 예제

<form method="post" action="#">
	<fieldset style="float: left; border: 1px solid #888; padding: 5px; margin-right: 10px;">
		<legend>Shipping Address:</legend>
		<div>
			<label for="shipping_name"><span class="visuallyhidden">Shipping </span>Name:</label><br>
			<input type="text" name="shipping_name" id="shipping_name">
		</div>
		<div>
			<label for="shipping_street">Street:</label><br>
			<input type="text" name="shipping_street" id="shipping_street">
		</div>
		<div>
			<label for="shipping_number">Number:</label><br>
			<input type="text" name="shipping_number" id="shipping_number">
		</div>
		<div>
			<label for="shipping_city">City:</label><br>
			<input type="text" name="shipping_city" id="shipping_city">
		</div>
		<div>
			<label for="shipping_zip">ZIP code:</label><br>
			<input type="text" name="shipping_zip" id="shipping_zip">
			</div>
	</fieldset>
	<fieldset style="float: left; border: 1px solid #888; padding: 5px;">
		<legend>Billing Address:</legend>
		<div>
			<label for="billing_name"><span class="visuallyhidden">Billing </span>Name:</label><br>
			<input type="text" name="billing_name" id="billing_name">
		</div>
		<div>
			<label for="billing_street">Street:</label><br>
			<input type="text" name="billing_street" id="billing_street">
		</div>
		<div>
			<label for="billing_number">Number:</label><br>
			<input type="text" name="billing_number" id="billing_number">
		</div>
		<div>
			<label for="billing_city">City:</label><br>
			<input type="text" name="billing_city" id="billing_city">
		</div>
		<div>
			<label for="billing_zip">ZIP code:</label><br>
			<input type="text" name="billing_zip" id="billing_zip">
		</div>
	</fieldset>
</form>

###### 코드 스니펫

```
<fieldset>
	<legend>Shipping Address:</legend>
	<div>
		<label for="shipping_name">
      <span class="visuallyhidden">Shipping </span>Name:
    </label><br>
		<input type="text" name="shipping_name" id="shipping_name">
	</div>
  <div>
    <label for="shipping_street">Street:</label><br>
    <input type="text" name="shipping_street" id="shipping_street">
  </div>
	[…]
</fieldset>
<fieldset>
	<legend>Billing Address:</legend>
	<div>
		<label for="billing_name">
      <span class="visuallyhidden">Billing </span>Name:
    </label><br>
		<input type="text" name="billing_name" id="billing_name">
	</div>
  <div>
    <label for="billing_street">Street:</label><br>
    <input type="text" name="billing_street" id="billing_street">
  </div>
	[…]
</fieldset>
```

> 참고
>
> 일부 화면 리더는 구성에 따라 범례를 _모든 양식 요소와 함께_, _한 번만_, 또는 드물게는 _전혀 _ 읽지 않습니다.
> 이를 위해 다음 사항을 고려하세요.
>
> - 매번 레이블과 함께 읽어야 하는 상황에서는 범례를 최대한 짧게 만드세요.
> - 모든 레이블에서 범례를 반복하지 않고 범례를 소리 내어 읽지 않는 상황에 대비하여 개별 레이블을 충분히 직관적으로 설명할 수 있게 만드세요.

### [연관된 컨트롤을 WAI-ARIA로 연결하기](https://www.w3.org/WAI/tutorials/forms/grouping/#associating-related-controls-with-wai-aria)

WAI-ARIA는 `fieldset` 및 `legend`와 유사한 기능을 하는 그룹화 역할을 제공합니다.
이 예에서 `div` 요소에는 `role=group`이 있어 포함된 요소가 그룹의 멤버임을 나타내며 `aria-labelledby` 속성은 그룹의 레이블 역할을 할 텍스트에 대한 `id`를 참조합니다.

이 기술은 추가적인 스타일링의 가능성을 제공합니다.

###### 예제

<form method="post" action="#">
	<div role="group" aria-labelledby="shipping_head" style="float: left; border: 1px solid #333; padding: 0 .5em .5em; margin-right: 1em;">
		<div id="shipping_head" style="font-weight: bold; padding: .25em 0;">Shipping Address:</div>
		<div>
			<label for="aria_shipping_name"><span class="visuallyhidden">Shipping </span>Name:</label><br>
			<input type="text" name="aria_shipping_name" id="aria_shipping_name">
		</div>
		<div>
			<label for="aria_shipping_street">Street:</label><br>
			<input type="text" name="aria_shipping_street" id="aria_shipping_street">
		</div>
		<div>
			<label for="aria_shipping_number">Number:</label><br>
			<input type="text" name="aria_shipping_number" id="aria_shipping_number">
		</div>
		<div>
			<label for="aria_shipping_city">City:</label><br>
			<input type="text" name="aria_shipping_city" id="aria_shipping_city">
		</div>
		<div>
			<label for="aria_shipping_zip">ZIP code:</label><br>
			<input type="text" name="aria_shipping_zip" id="aria_shipping_zip">
			</div>
	</div>
	<div role="group" aria-labelledby="billing_head" style="float: left; border: 1px solid #333; padding: 0 .5em .5em;">
		<div id="billing_head" style="font-weight: bold; padding: .25em 0;">Billing Address:</div>
		<div>
			<label for="aria_billing_name"><span class="visuallyhidden">Billing </span>Name:</label><br>
			<input type="text" name="aria_billing_name" id="aria_billing_name">
		</div>
		<div>
			<label for="aria_billing_street">Street:</label><br>
			<input type="text" name="aria_billing_street" id="aria_billing_street">
		</div>
		<div>
			<label for="aria_billing_number">Number:</label><br>
			<input type="text" name="aria_billing_number" id="aria_billing_number">
		</div>
		<div>
			<label for="aria_billing_city">City:</label><br>
			<input type="text" name="aria_billing_city" id="aria_billing_city">
		</div>
		<div>
			<label for="aria_billing_zip">ZIP code:</label><br>
			<input type="text" name="aria_billing_zip" id="aria_billing_zip">
		</div>
	</div>
</form>

모든 웹 브라우저 및 화면 리더 조합에서 WAI-ARIA가 완벽하게 지원되는 것은 아니므로 그룹의 첫 번째 양식 컨트롤에 그룹 식별자를 추가해야 합니다.

###### 코드 스니펫

```
<div role="group" aria-labelledby="shipping_head">
	<div id="shipping_head">Shipping Address:</div>
	<div>
		<label for="shipping_name">
      <span class="visuallyhidden">Shipping </span>Name:
    </label><br>
		<input type="text" name="shipping_name" id="shipping_name">
	</div>
	[…]
</div>
<div role="group" aria-labelledby="billing_head">
	<div id="billing_head">Billing Address:</div>
	<div>
		<label for="billing_name">
      <span class="visuallyhidden">Billing </span>Name:
    </label><br>
		<input type="text" name="billing_name" id="billing_name">
	</div>
	[…]
</div>
```

### [`select` 요소의 항목 그룹화](https://www.w3.org/WAI/tutorials/forms/grouping/#grouping-items-in-select-elements)

옵션 그룹이 있는 `select` 요소의 경우 `optgroup` 요소를 사용하여 해당 그룹을 표시할 수 있습니다.
`optgroup` 요소의 `label` 속성은 그룹에 대한 레이블을 제공하는 데 사용됩니다.
이는 관련 옵션이 많은 목록에 특히 유용합니다.
아래 예제에서 사용자는 세 가지 코스 중 하나의 강의를 선택할 수 있습니다.

###### 예제

<form action="#" method="get">
	<fieldset>
		<legend>Which course would you like to watch today?</legend>
		<label for="course">Course:</label>
		<select name="course" id="course">
			<option></option>
			<optgroup label="8.01 Physics I: Classical Mechanics">
				<option value="8.01.1">Lecture 01: Powers of Ten</option>
				<option value="8.01.2">Lecture 02: 1D Kinematics</option>
				<option value="8.01.3">Lecture 03: Vectors</option>
			</optgroup>
			<optgroup label="8.02 Physics II: Electricity and Magnestism">
				<option value="8.02.1">Lecture 01: What holds our world together?</option>
				<option value="8.02.2">Lecture 02: Electric Field</option>
				<option value="8.02.3">Lecture 03: Electric Flux</option>
			</optgroup>
			<optgroup label="8.03 Physics III: Vibrations and Waves">
				<option value="8.03.1">Lecture 01: Periodic Phenomenon</option>
				<option value="8.03.2">Lecture 02: Beats</option>
				<option value="8.03.3">Lecture 03: Forced Oscillations with Damping</option>
			</optgroup>
		</select>
		<input class="button" type="submit" value="▶ Play">
	</fieldset>
</form>

###### 코드 스니펫

```
<select>
	<optgroup label="8.01 Physics I: Classical Mechanics">
		<option value="8.01.1">Lecture 01: Powers of Ten</option>
		<option value="8.01.2">Lecture 02: 1D Kinematics</option>
		<option value="8.01.3">Lecture 03: Vectors</option>
	</optgroup>
	<optgroup label="8.02 Physics II: Electricity and Magnestism">
		<option value="8.02.1">Lecture 01: What holds our world together?</option>
		[…]
	</optgroup>
	[…]
</select>
```

## [양식 지침](https://www.w3.org/WAI/tutorials/forms/instructions/)

사용자가 양식을 작성하고 개별 양식 컨트롤을 사용하는 방법을 이해하는 데 도움이 되는 지침을 제공하세요.
필수 및 선택 입력, 데이터 형식 및 기타 관련 정보를 표시합니다.

**중요:** 화면 리더는 종종 `<form>` 요소 내의 콘텐츠를 처리할 때 '양식 모드'로 전환합니다.
이 모드에서는 일반적으로 `<input>`, `<select>`, `<textarea>`, `<legend>`, `<label>`과 같은 양식 요소만 소리내어 읽습니다.
소리내어 읽을 수 있는 방식으로 양식 지침을 포함하는 것이 중요합니다.
이에 대해서는 아래에서 자세히 설명합니다.

### [전체 지침](https://www.w3.org/WAI/tutorials/forms/instructions/#overall-instructions)

해당하는 경우 전체 양식에 적용되는 전반적인 지침을 제공합니다.
예를 들어 필수 및 선택 입력, 허용되는 데이터 형식 및 시간 제한을 표시합니다.
이러한 지침은 `<form>` 요소 앞에 제공하여 화면 리더가 '양식 모드'로 전환하기 전에 소리로 읽을 수 있도록 하세요.

아래 예제에서는 양식 지침에 필수 필드가 표시되는 방법, 주요 데이터 필드의 예상 형식, 각 입력에 대한 추가 도움말을 찾을 수 있는 위치가 나와 있습니다.

###### 예제

- All fields marked “required” must be completed.
- Dates should all be typed in the format dd/mm/yyyy, (as in 21/07/2013).
- Passwords must contain at least 8 letters and/or numbers.
- Extra help can be found immediately after each field.

### [인라인 지침](https://www.w3.org/WAI/tutorials/forms/instructions/#in-line-instructions)

전체 지침 외에도 양식 컨트롤의 레이블 내에 관련 지침을 제공하는 것도 중요합니다.
예를 들어 레이블의 텍스트에 필수 입력 필드와 데이터 형식을 표시할 수 있습니다.

#### [레이블 내에 지침 제공](https://www.w3.org/WAI/tutorials/forms/instructions/#providing-instructions-within-labels)

간단한 사용 사례의 경우 레이블 내에 지침을 제공하는 것으로 충분할 수 있습니다.
이 접근 방식은 다양한 웹 브라우저와 보조 기술에서 안정적으로 사용할 수 있지만 일부 스타일링 요구 사항을 지원하려면 추가적인 고려가 필요할 수 있습니다.

아래 예시에서 'Expiration date'의 필수 형식은 동일한 레이블 내에서 'MM/YYYY'로 표시됩니다:

###### 예제

<form method="post" action="#">
	<div>
		<label for="expire">Expiration date (MM/YYYY): </label> <input type="text" name="expire" id="expire">
	</div>
</form>

###### 코드 스니펫

```
<label for="expire">Expiration date (MM/YYYY): </label>
<input type="text" name="expire" id="expire">
```

#### [레이블 외부에 지침 제공](https://www.w3.org/WAI/tutorials/forms/instructions/#providing-instructions-outside-labels)

레이블 외부에 지침을 제공하면 보다 유연하게 위치를 지정하고 디자인할 수 있지만 간혹 이를 놓칠 수 있습니다.
또한 일부 웹 브라우저(일반적으로 이전 버전)와 WAI-ARIA를 구현하지 않는 보조 기술에서는 지원되지 않습니다.

##### [`aria-labelledby` 사용](https://www.w3.org/WAI/tutorials/forms/instructions/#using-aria-labelledby)

한 가지 접근 방식은 WAI-ARIA `aria-labelledby` 속성을 사용하여 지침을 양식 컨트롤과 연결하는 것입니다.
이 튜토리얼을 작성하는 시점에서 이 접근 방식은 모든 웹 브라우저 및 보조 기술(예: 점자 디스플레이)에서 완벽하게 지원되지는 않습니다.
이전 버전과의 호환성을 보장하기 위해 이 예제에서는 `for` 및 `id` 속성도 사용됩니다.

###### 예제

<div class="box-i">

<style>
	#ex3 span {
		display: inline-block;
		vertical-align: top;
	}
	#ex3 span span {
		display: block;
		font-size: 0.8em;
	}
</style>

<form method="post" action="#" id="ex3">
	<div>
		<label id="expLabel" for="expire4">Expiration date:</label>
		<span>
			<input type="text" name="expire" id="expire4" aria-labelledby="expLabel expDesc2">
			<span id="expDesc2">MM/YYYY</span>
		</span>
	</div>
</form>

</div>

###### 코드 스니펫

```
<label id="expLabel" for="expire">Expiration date:</label>
<span>
	<input type="text" name="expire" id="expire" aria-labelledby="expLabel expDesc">
	<span id="expDesc">MM/YYYY</span>
</span>
```

##### [`aria-describedby` 사용](https://www.w3.org/WAI/tutorials/forms/instructions/#using-aria-describedby)

추가 지침을 양식 필드에 연결하는 또 다른 접근 방식은 `aria-describedby`를 사용하는 것입니다.
이 속성에 의해 참조되는 정보는 레이블 및 기타 정보가 공개된 후에 사용자에게 제공됩니다.

###### 코드 스니펫

```
<label id="expLabel" for="expire">Expiration date:</label>
<span>
	<input type="text" name="expire" id="expire" aria-labelledby="expLabel" aria-describedby="expDesc">
	<span id="expDesc">MM/YYYY</span>
</span>
```

#### [플레이스홀더 텍스트](https://www.w3.org/WAI/tutorials/forms/instructions/#placeholder-text)

플레이스홀더 텍스트는 사용자가 아직 편집하지 않은 양식 필드 안에 필요한 데이터 형식에 대한 지침이나 예시를 제공합니다.
플레이스홀더 텍스트는 일반적으로 사용자가 제공한 텍스트보다 낮은 색상 대비로 표시되며, 사용자가 텍스트 입력을 시작하면 양식 필드에서 사라집니다.
플레이스홀더 텍스트에 사라지는 지침 정보나 예시가 포함되어 있으면 사용자가 양식을 제출하기 전에 자신의 응답을 확인하기가 더 어려워집니다.

플레이스홀더 텍스트는 많은 사용자에게 유용한 안내를 제공하지만 **플레이스홀더 텍스트는 레이블을 대체할 수 없습니다**.
화면 리더와 같은 보조 기술은 플레이스홀더 텍스트를 레이블로 취급하지 않습니다.
또한 이 튜토리얼을 작성하는 시점에서 플레이스홀더 텍스트는 보조 기술 전반에서 광범위하게 지원되지 않으며 구형 웹 브라우저에서는 표시되지 않습니다.

> 참고
>
> 컨트롤에 레이블 지정하기 페이지의 [요소 숨기기 관련 참고 사항](https://www.w3.org/WAI/tutorials/forms/labels/#note-on-hiding-elements) 섹션에서는 정보를 시각적으로 숨기되 보조 기술에서 계속 사용할 수 있도록 하는 방법에 대해 설명합니다.
> 이와 동일한 접근 방식을 사용하여 레이블과 플레이스홀더 텍스트가 모두 표시되는 시각적 중복을 피할 수 있습니다.
> 이렇게 하면 사용자가 양식을 검토하기가 매우 어렵다는 점에 유의하세요.
> 이 문제를 방지하려면 자바스크립트를 사용하여 레이블이 초점이 있는 입력의 위나 옆에 시각적으로(연결된 레이블 요소에) 표시되도록 할 수 있습니다.

###### 예제

<div class="box-i">

<form method="post" action="#">
	<div>
		<label for="search">Search:</label> <input type="text" name="search" id="search" placeholder="e.g. Apple Pie">
	</div>
	<div>
		<label for="email">Email: </label> <input type="text" name="email" id="email" placeholder="joe@example.com">
	</div>
</form>

<style>
::-webkit-input-placeholder {
	 color: #777;
	 opacity: 1;
}

:-moz-placeholder { /* Firefox 18- */
	 color: #777;
	 opacity: 1;
}

::-moz-placeholder {  /* Firefox 19+ */
	 color: #777;
	 opacity: 1;
}

:-ms-input-placeholder {
	 color: #777;
	 opacity: 1;
}
</style>

</div>

###### 코드 스니펫

```
<div>
	<label for="search">Search:</label> <input type="text" name="search" id="search" placeholder="e.g. Apple Pie">
</div>
<div>
	<label for="email">Email: </label> <input type="text" name="email" id="email" placeholder="joe@example.com">
</div>
```

##### [스타일링](https://www.w3.org/WAI/tutorials/forms/instructions/#styling)

이 튜토리얼을 작성하는 시점에서 웹 브라우저는 일반적으로 플레이스홀더 텍스트를 [WCAG의 최소 색상 대비 요구 사항](https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum)을 충족하지 않는 색상으로 표시합니다.
이는 많은 사람들이 보기 어렵다는 것을 의미합니다.
웹 브라우저는 이 효과를 내기 위해 색상과 불투명도를 조합하여 사용합니다.
대부분의 웹 브라우저에서 플레이스홀더의 색상은 전용 CSS 선택기를 사용하여 스타일을 지정할 수 있습니다.
다음 코드 스니펫은 요소의 배경이 흰색이라고 가정할 때 대비 요구 사항을 충족하기에 충분한 대비를 가진 밝은 회색으로 색상을 설정합니다.

###### 코드 스니펫

```
::placeholder {
	 color: #767676;
	 opacity: 1;
}
```

## [입력 유효성 검사](https://www.w3.org/WAI/tutorials/forms/validation/)

지침을 제공하는 것 외에도 사용자 입력의 유효성을 검사하여 사용자가 실수를 방지할 수 있도록 하세요.
HTML5는 이메일 주소, 날짜 등 일반적인 입력 유형의 유효성을 검사하는 다양한 기본 제공 기능을 정의합니다.
사용자 지정 컨트롤의 유효성 검사나 레거시 브라우저 지원과 같은 일부 상황에서는 사용자 입력의 유효성을 검사하기 위해 추가 스크립팅이 필요할 수 있습니다.

사용자 정의 유효성 검사는 이 튜토리얼의 [사용자 알림](https://www.w3.org/WAI/tutorials/forms/notifications/) 부분에 설명된 대로 사용자에게 접근 가능한 방식으로 알려야 합니다.
클라이언트 측 유효성 검사만으로는 보안을 보장할 수 없으므로 서버 측에서도 데이터를 유효성 검사해야 합니다.

### [필수 입력 유효성 검사](https://www.w3.org/WAI/tutorials/forms/validation/#validating-required-input)

양식에는 레이블을 사용하여 명확하게 식별해야 하는 필수 입력이 포함되어 있는 경우가 많습니다.
또한 양식 컨트롤에 `required` 속성을 추가하여 프로그래밍 방식으로 필수임을 표시할 수 있습니다.
대부분의 최신 웹 브라우저는 이 속성을 지원하며 표준 웹 브라우저 대화 상자 메커니즘을 사용하여 누락된 필수 입력을 사용자에게 전달합니다.
이러한 대화 상자는 기본 글꼴 크기, 색상, 언어 등 웹 브라우저(및 운영 체제)에서 사용자의 설정 및 기본 설정을 준수해야 합니다.

아래 예제에서는 입력 필드에 `required` 속성이 추가되었습니다.
웹 브라우저가 HTML5를 지원하는 경우 입력 필드에 텍스트를 입력하지 않으면 양식을 제출할 수 없습니다.
대신 웹 브라우저 자체에서 생성된 메시지가 표시됩니다.

보조 기술을 사용하지 않거나 HTML5 `required` 속성을 지원하지 않는 구형 웹 브라우저를 사용하는 사용자에게 알리기 위해 라벨에 '(필수)'가 표시되어 있습니다.

###### 예제

<form method="post" action="../../beyond/">
	<div>
		<label for="name">Name (required): </label> <input type="text" name="name" id="name" required="" aria-required="true">
		<input type="submit" value="Submit">
	</div>
</form>

###### 코드 스니펫

```
<label for="name">Name (required): </label>
<input type="text" name="name" id="name" required aria-required="true">
```

> 참고
>
> `aria-required` 속성은 보조 기술에 필요한 컨트롤에 대한 정보를 제공하여 사용자에게 적절하게 알릴 수 있도록 합니다(입력의 유효성을 검사하는 것과는 대조적으로).
> 대부분의 최신 웹 브라우저는 HTML5 `required` 속성이 있으면 자동으로 해당 값을 `true`로 설정합니다.
> 이 예제에서는 보조 기술에 `required` 속성을 전달하지 않는 웹 브라우저를 지원하기 위해 중복으로 제공됩니다.

### [일반 입력 유효성 검사](https://www.w3.org/WAI/tutorials/forms/validation/#validating-common-input)

HTML5는 `email`, `url`, `number`, `range`, `date`, `time` 등 다른 데이터에 대한 입력 유형도 제공합니다.
대부분의 최신 웹 브라우저는 이러한 기능을 지원하며 입력 유효성 검사를 처리합니다.
또한 HTML5 유효성 검사는 날짜 선택기 및 사용자 지정 온스크린 키보드와 같은 특정 컨트롤을 제공하여 사용자가 데이터를 입력하는 데 도움을 줍니다.
HTML5 입력 유형은 이러한 HTML5 기능을 지원하지 않는 구형 웹 브라우저에서는 단순한 `text` 입력 필드로 표시됩니다.

아래 예제는 이러한 HTML5 입력 유형이 실제로 작동하는 모습을 보여줍니다.
웹 브라우저에 따라 '범위' 입력 필드가 슬라이더 컨트롤로 표시되어 사용자가 보다 쉽게 입력할 수 있습니다.
마찬가지로 '숫자' 입력 필드에는 숫자를 점진적으로 늘리거나 줄일 수 있는 버튼이 표시될 수 있습니다.
잘못된 이메일 주소와 같은 입력 오류는 이전 예에서와 같이 웹 브라우저 대화 상자를 사용하여 표시됩니다.

###### 예제

<div class="box-i">

<form method="post" action="../../beyond/" id="valform">
	<div>
		<div><label for="email">Email: </label></div>
		<div><input type="email" name="email" id="email"></div>
	</div>
	<div>
		<div><label for="url">Website: </label></div>
		<div><input type="url" name="url" id="url"></div>
	</div>
	<div>
		<div><label for="number">Number: </label></div>
		<div><input type="number" name="number" id="number" min="0" max="100" step="10" value="0"></div>
	</div>
	<div>
		<div><label for="range">Range: </label></div>
		<div><input type="range" name="range" id="range" min="0" max="100" step="10" value="0"></div>
	</div>
	<div>
		<div><label for="date">Date: </label></div>
		<div><input type="date" name="date" id="date"></div>
	</div>
	<div>
		<div><label for="time">Time: </label></div>
		<div><input type="time" name="time" id="time"></div>
	</div>
	<div>
		<div></div>
		<div><input type="submit" value="Submit"></div>
	</div>
</form>

<style>
	#valform {display:table}
	#valform>div {display:table-row}
	#valform>div>div {display:table-cell; padding: .1em;}
</style>

</div>

###### 코드 스니펫

```
<div>
	<label for="email">Email: </label>
	<input type="email" name="email" id="email">
</div>
<div>
	<label for="url">Website: </label>
	<input type="url" name="url" id="url">
</div>
<div>
	<label for="number">Number: </label>
	<input type="number" name="number" id="number" min="0" max="100" step="10" value="0">
</div>
<div>
	<label for="range">Range: </label>
	<input type="range" name="range" id="range" min="0" max="100" step="10" value="0">
</div>
<div>
	<label for="date">Date: </label>
	<input type="date" name="date" id="date">
</div>
<div>
	<label for="time">Time: </label>
	<input type="time" name="time" id="time">
</div>
```

> 참고
>
> 이러한 HTML5 입력 유형 중 몇 가지에는 입력을 제한하고 유효성을 검사하는 데 도움이 되는 추가 매개변수가 있습니다. 여기에는 다음이 포함됩니다:
>
> - `maxlength`는 텍스트 필드의 최대 길이를 정의합니다.
> - `min` 및 `max`는 `number` 및 `range` 필드의 최소값과 최대값을 정의합니다.
> - `steps`는 숫자 및 범위 필드를 몇 단계로 증가 및 감소시킬 수 있는지 정의합니다.

### [패턴 입력 유효성 검사](https://www.w3.org/WAI/tutorials/forms/validation/#validating-patterned-input)

HTML5 `pattern` 속성을 사용하면 [정규식](https://www.w3.org/TR/html/forms.html#the-pattern-attribute)을 사용하여 입력에 대한 사용자 지정 형식을 지정할 수 있습니다.
이는 전화번호, 우편번호, 일련번호와 같은 특정 유형의 데이터 패턴에 유용합니다.

#### [자동차 번호판 번호](https://www.w3.org/WAI/tutorials/forms/validation/#car-license-plate-numbers)

아래 예제에서 `input` 요소의 `pattern` 속성은 독일의 자동차 번호판(등록) 번호와 일치하는 특정 형식을 지정합니다.
필수 패턴은 1~3개의 문자(자동차가 등록된 도시의 경우), 공백, 2~4개의 임의 문자, 또 다른 공백, 1~4개의 임의 숫자로 구성됩니다.

###### 예제

<form method="post" action="../../beyond/">
	<div>
		<label for="license">German License Plate (CCC XXXX 9999):</label> <input type="text" id="license" pattern="[A-ZÖÄÜ]{1,3} [A-Z]{2,4} [0-9]{1,4}">
	</div>
	<div>
	</div>
</form>

###### 코드 스니펫

```
<div>
	<input type="text" id="license"
		pattern="[A-ZÖÄÜ]{1,3} [A-Z]{2,4} [0-9]{1,4}"
	>
</div>
```

### [다양한 입력 형식 허용](https://www.w3.org/WAI/tutorials/forms/validation/#be-forgiving-of-different-input-formats)

유효성 검사는 특정 데이터 유형에 대해 가능한 한 다양한 형태의 입력을 수용하는 것을 목표로 해야 합니다.
예를 들어 전화번호는 서로 다른 구분 기호 및 숫자 그룹으로 작성됩니다.
여러 표기법을 해석할 수 있다면 양식을 사용하기가 더 쉬워집니다.
또한 자유롭게 입력하는 것이 도움이 됩니다.
예를 들어 우편 번호는 일부 국가에서는 숫자로만 제한되지 않으므로 `number` 유형의 `input`을 사용하면 많은 웹사이트 사용자에게 쉽게 문제가 될 수 있습니다.

### [클라이언트 측 유효성 검사 혜택](https://www.w3.org/WAI/tutorials/forms/validation/#client-side-validation-benefits)

일반적으로 클라이언트 측 유효성 검사는 사용자 경험을 개선하고 유효성 검사 오류를 더 쉽게 해결할 수 있게 해줍니다.
또한 네트워크 및 서버 부하를 줄일 수 있습니다.
하지만 모든 웹 브라우저가 HTML5를 지원하는 것은 아니거나 사용자 지정 유효성 검사 스크립트를 지원하지 않을 수도 있습니다.
클라이언트 측 유효성 검사를 쉽게 우회하거나 데이터가 서버에 도달하기 전에 변경될 수도 있습니다.
즉, 서버 측에서도 유효성 검사를 수행해야 합니다.

### [사용자에 의한 유효성 검사](https://www.w3.org/WAI/tutorials/forms/validation/#validation-by-the-user)

가능하면 사용자가 자신의 입력을 확인하고 필요한 경우 수정할 수 있어야 합니다.
이는 영구적이거나 기타 중요한 작업의 경우 특히 중요하지만, 데이터를 자동으로 확인할 수 없는 경우에도 마찬가지입니다.
예를 들어, 사용자가 제공한 우편 주소를 확인할 수 있는 옵션을 제공하면 구매가 완료되기 전에 유용할 수 있습니다.

#### [사용자 확인 필요](https://www.w3.org/WAI/tutorials/forms/validation/#require-user-confirmation)

가능한 경우 데이터 영구 삭제와 같은 되돌릴 수 없는 작업은 사용자 확인을 받도록 합니다. 예를 들면 다음과 같습니다:

- CMS를 사용하면 사용자가 휴지통 폴더에서 댓글을 영구 삭제할 수 있습니다. 이 작업이 시작되면 사용자에게 작업을 확인하는 대화 상자가 표시됩니다.
- 은행 애플리케이션에서는 사용자가 '이체하려는 금액이 정확한지 확인했습니다'라는 확인란을 선택하여 이체 거래를 확인하도록 요구합니다.
- 쇼핑 웹사이트에서는 구매 거래가 완료되고 주문이 접수되기 전에 사용자가 확인해야 하는 주문, 배송 주소 및 청구 정보 요약이 표시됩니다.

#### [실행 취소 기능 제공](https://www.w3.org/WAI/tutorials/forms/validation/#provide-undo-functionality)

가능하면 되돌릴 수 있는 작업을 취소할 수 있는 메커니즘을 제공하세요. 예를 들면 다음과 같습니다:

- 콘텐츠 관리 시스템(CMS)에서 원치 않는 댓글을 삭제할 수 있습니다. 댓글을 바로 삭제하는 대신 '휴지통' 폴더에 저장하여 복원할 수 있도록 합니다.
- 웹메일 애플리케이션을 사용하면 몇 초 동안 이메일 전송을 '취소'할 수 있습니다. 이 기능은 사용자가 파일을 첨부하는 것을 잊었거나 잘못된 수신자에게 이메일을 보낸 경우에 유용합니다.
- 쇼핑 웹사이트에서는 주문이 제출된 후 최대 24시간까지 구매를 취소할 수 있습니다. 웹사이트는 정책을 설명하고 사용자에게 이메일로 전송된 구매 영수증에 정책 요약본을 포함합니다. 24시간이 지나면 구매 제품이 사용자에게 배송되며 더 이상 취소할 수 없습니다.

## [사용자 알림](https://www.w3.org/WAI/tutorials/forms/notifications/)

## Overview

Provide feedback to users about the results of their form submission, whether successful or not.
This includes in-line feedback at or near the form controls and overall feedback that is typically provided after form submission.

Page Contents

- [Overall feedback](#overall-feedback)
  - [Using the main heading](#using-the-main-heading)
  - [Using the page title](#using-the-page-title)
  - [Using dialogs](#using-dialogs)
  - [Listing errors](#listing-errors)
- [In-line feedback](#inline)
  - [After submit](#after-submit)
  - [During typing](#during-typing)
    - [Binary messages](#binary-messages)
    - [Scaled feedback](#scaled-feedback)
  - [On focus change](#on-focus-change)

Notifications have to be concise and clear. In particular, error messages should be easy to understand and should provide simple instructions on how they can be resolved. Success messages are also important to confirm task completion.

## Overall feedback

When a form is submitted, it is important that the user is notified whether the submission was successful or if errors occurred. Several of the following techniques can be combined.

### Using the main heading

A common way to provide feedback is by using the main heading of the web page, usually, the most prominently displayed `<h1>` or `<h2>` element. This technique is particularly useful when forms are processed by the server, but can also be useful for client-side scripting.

Code: Error

```
<h1>3 Errors – Billing Address</h1>
```

Code: Success

```
<h1>Thank you for submitting your order.</h1>
```

Note

The primary purpose of the main heading is still to identify the web page that the user is currently on. When the user is sent back to the same web page because of an error, then a simple indication using the word “error” and possibly the number of errors is helpful.

### Using the page title

The `<title>` element of the web page can be useful to indicate successes and errors. In particular, screen reader users will receive this feedback immediately when the web page is loaded. This can be helpful when the main heading is located deeper within the content, for example, after the navigation menus.

Code: Error

```
<title>3 Errors – Billing Address</title>
```

Code: Success

```
<title>Thank you for submitting your order.</title>
```

### Using dialogs

A dialog is a common way to inform users of changes. It can be used if other means of informing the user prove to be easily missed. Dialogs are more obtrusive and distracting, which may be the desired effect.

JavaScript provides a very basic alert dialog box that provides proper keyboard navigation and respects the user’s default settings, including font size, colors, and language. A custom dialog implementation has to match that functionality.

The basic example below shows a pop-up that is displayed when the user activates the “save” button. A message is displayed in the dialog box, and the web page is disabled until the user selects “OK”.

###### 예제

Save

document.getElementById('alertconfirm').addEventListener('click', function(){ alert('Thanks for submitting the form!'); });

Code: HTML

```
<button type="button" id="alertconfirm">Save</button>
```

Code: JavaScript

```
document.getElementById('alertconfirm')
	.addEventListener('click', function() {
		/* [… code saving data …] */
		alert('Thanks for submitting the form!');
	});
```

### Listing errors

When errors occur, it is helpful to list them at the top of the page, before the form. The list should have a distinctive heading so that it is easy to identify. Each error listed should:

- Reference the label of the corresponding form control, to help the user recognize the control;
- Provide a concise description of the error in a way that is easy to understand by everyone;
- Provide an indication of how to correct mistakes, and remind users of any format requirements;
- Include an in-page link to the corresponding form control to make access easier for the users.

Sometimes, for example, when using AJAX techniques, the browser is not loading a new page but shows changes, such as form errors, dynamically on the page. The list of errors should be inserted into a prominent container on the top to inform the user in such a case. In addition to the advice above, this container should have the `role` attribute set to `alert` to make assistive technology users aware of this change.

###### 예제

#### There are 2 errors in this form

- [The First name field is empty, it is a required field and must be filled in.](#firstname)
- [The Date field is in the wrong format, it should be similar to 17/09/2013 (use a / to separate day, month, and year).](#birthdate)

###### 코드 스니펫

```
<div role="alert">
  <h4>There are 2 errors in this form</h4>
  <ul>
  	<li>
  		<a href="#firstname" id="firstname_error">
  			The First name field is empty; it is a required field and must be filled in.
  		</a>
  	</li>
  	<li>
  		<a href="#birthdate" id="birthdate_error">
  			The Date field is in the wrong format; it should be similar to 17/09/2013 (use a / to separate day, month, and year).
  		</a>
  	</li>
  </ul>
</div>
```

Also, form fields can be associated with the corresponding error message using aria-describedby.

###### 코드 스니펫

```
<label for="firstname">First Name:</label>
<input type="text" id="firstname" aria-describedby="firstname_error">
```

## In-line feedback

In addition to overall feedback, more specific feedback at or near the form controls can better help users to use your form. This includes feedback to indicate correctly entered input as well as errors in the input.

Typically a combination of messages and visual cues are used to provide in-line feedback. For example, valid input can be indicated by a checkmark (✓) and green border, while errors can be indicated by an error icon (like a red ✗ or an exclamation mark) and red border. Error messages should also provide guidance on how to correct mistakes. The concepts for such error messages are essentially the same as for providing [instructions](https://www.w3.org/WAI/tutorials/forms/instructions).

### After submit

The example below shows a form with two input fields. The first input field, “username”, is used to register a username. The second input field, “expiry date”, is used to provide a date for when the registration expires.

When the form is submitted, the entries are checked, and feedback is provided to the user. Appropriate success and error messages are displayed for each input field to help the user complete the form.

If the submitted data contains errors, it is convenient to set the focus to the first `<input>` element that contains an error.

###### 예제

#ex3 div {margin-bottom:.75em;} .error { color: #900; } .error input { border: 3px solid #900; } .success { color: #007a00; } .success input { border: 3px solid #007a00; }

**OK:** Username: ✓

**Error:** Expiry date: Use the format MM/YYYY.

Submit

var taken_usernames = \['timbl', 'shadi', 'yatil', 'bim', 'shawn', 'slh', 'spacebear13', 'Obelisks', 'Phoenix', 'Imari', 'Henry', 'Zeki', 'Rome', 'Min', ' Kelly', 'Brynn'\]; document.getElementById('ex3').addEventListener('submit', function(event){ function setError(el, msg) { el.parentNode.querySelector('strong').innerHTML = "Error:"; el.parentNode.className='error'; el.parentNode.querySelector('span').innerHTML = msg; } function setSuccess(el) { el.parentNode.querySelector('strong').innerHTML = "OK:"; el.parentNode.className='success'; el.parentNode.querySelector('span').innerHTML = "&check;"; } var exp = document.getElementById('expire4'); if (exp.value.match(new RegExp('\[0-9\]{2}\\/\[0-9\]{4}'))) { setSuccess(exp); } else { setError(exp, 'Use the format MM/YYYY.'); } var usr = document.getElementById('username4'); if (taken_usernames.includes(usr.value.trim()) == false) { setSuccess(usr); } else { setError(usr, 'Username already taken'); } event.preventDefault(); return false; });

Code: HTML

```
<div class="success">
	<label for="username">
		<strong>OK:</strong> Username:
	</label>
	<input type="text" name="username"
		id="username" value="spaceteddy13"
		aria-describedby="userDesc">
	<span id="userDesc">✓</span>
</div>
<div class="error">
	<label for="expire">
		<strong>Error:</strong>
		Expiry date:
	</label>
	<input type="text" name="expire"
		id="expire" value="03.2015"
		aria-describedby="expDesc">
		<span id="expDesc">Use the format MM/YYYY.</span>
</div>
<div>
	<button type="submit">Submit</button>
</div>
```

Code: CSS

```
.error   { color: #900; }
.success { color: #007a00; }
.error   input { border: 3px solid #900; }
.success input { border: 3px solid #007a00; }
```

### During typing

Instant feedback during typing can be extremely helpful. For example, checking the availability of a username in the previous example required the user to resubmit the form – possibly multiple times. Providing feedback while users are typing allows them to experiment more easily until they find a suitable username. However, client-side scripting is required for such functionality, and not all situations may be appropriate for such feedback.

#### Binary messages

In the following example, the availability of a username is checked instantly while the user is typing text in the input field. Corresponding success and error messages are displayed without the user needing to submit the form.

###### 예제

Username:

document.getElementById('ex1_username').addEventListener('keyup', function(){ function setError(el, msg) { el.parentNode.querySelector('strong').innerHTML = "Error:"; el.parentNode.className='error'; el.parentNode.querySelector('span').innerHTML = msg; } function setSuccess(el) { el.parentNode.querySelector('strong').innerHTML = "OK:"; el.parentNode.className='success'; el.parentNode.querySelector('span').innerHTML = "&check;"; } var val = this.value; if (val !== "") { if (taken_usernames.includes(val.trim())) { setError(this, '&cross; Sorry, this username is taken.'); } else { setSuccess(this, '&check; You can use this username.'); } } else { document.getElementById('username_feedback').innerHTML = ''; document.getElementById('username_feedback').parentNode.className = ''; document.querySelector('\[for="ex1_username"\] strong').innerHTML = ''; } });

Code: HTML

```
<div>
	<label for="username">Username:</label>
	<input type="text" name="username" id="username">
	<span id="username_feedback" aria-live="polite"></span>
</div>
```

Code: JavaScript

```
document.getElementById('username').addEventListener('keyup', function(){
	function setError(el, msg) {
		el.parentNode.querySelector('strong').innerHTML = "Error:";
		el.parentNode.className='error';
		el.parentNode.querySelector('span').innerHTML = msg;
	}
	function setSuccess(el) {
		el.parentNode.querySelector('strong').innerHTML = "OK:";
		el.parentNode.className='success';
		el.parentNode.querySelector('span').innerHTML = "&check;";
	}
	var val = this.value;
	if (val !== "") {
		if (taken_usernames.includes(val.trim())) {
			setError(this, '&cross; Sorry, this username is taken.');
		} else {
			setSuccess(this, '&check; You can use this username.');
		}
	} else {
		document.getElementById('username_feedback').innerHTML = '';
		document.getElementById('username_feedback')
			.parentNode.className = '';
		document.querySelector('[for="username"] strong').innerHTML = '';
	}
});
```

Note

The displayed message in this example is coded using a `<span>` element that has an `aria-live` attribute with the value `polite`. The contents of this so called “live region” are conveyed to screen readers and other assistive technology. The value “polite” de-emphasizes the importance of the message and does not cause screen readers to interrupt their current tasks to read aloud this message. Thus the message is only read once when the user stops typing rather than on every keystroke that the user makes.

#### Scaled feedback

The example below illustrates a range of possible types of feedback in addition to success and error messages. In the example, the strength of the password is checked as it is typed by the user. The feedback indicates a scale of how strong the password is. The feedback is indicated using several cues, including color coding, a barometer, and label “Weak”, “Okay”, and “Strong”, as well as the time that would be needed to crack the password.

Note

No data is sent using the following example input field. The password is shown in plain text for demonstration purposes.

###### 예제

Password:

#passwordmeter { display:inline-block; width:125px; height: 20px; border: 1px solid #666; vertical-align:middle; } #passwordmeter span { display:inline-block; height:1em; background-color: gray; width:25px; height: 20px; } (function(){var a;a=function(){var a,b;b=document.createElement("script");b.src="/WAI/content-images/tutorials/forms/zxcvbn.js";b.type="text/javascript";b.async=!0;a=document.getElementsByTagName("script")\[0\];return a.parentNode.insertBefore(b,a)};null!=window.attachEvent?window.attachEvent("onload",a):window.addEventListener("load",a,!1)}).call(this); document.getElementById('ex2_password').addEventListener('keyup', function(){ var meter = document.querySelector('#passwordmeter span'); var msg = document.getElementById('passwordmessage'); var pw = zxcvbn(this.value); meter.style.width = (pw.score+1) \* 25 + 'px'; if (pw.score == 0) { meter.style.backgroundColor = 'red'; msg.innerHTML = '<strong>Really Weak</strong> Password'; } else if (pw.score < 3) { meter.style.backgroundColor = 'red'; msg.innerHTML = '<strong>Weak</strong> Password (cracked in ' + pw.crack_time_display + ')'; } else if (pw.score == 3) { meter.style.backgroundColor = 'yellow'; msg.innerHTML = '<strong>Good</strong> Password (cracked in ' + pw.crack_time_display + ')'; } else { meter.style.backgroundColor = 'green'; msg.innerHTML = '<strong>Strong</strong> Password (cracked in ' + pw.crack_time_display + ')'; } if (this.value == "") { meter.style.backgroundColor = 'gray'; msg.innerHTML = ' '; } });

[See commented example code in full.](https://www.w3.org/WAI/tutorials/forms/examples/password/)

### On focus change

In some cases, it does not make sense to check input as it is being typed by the user because it would display error messages most of the time. This is often the case when data needs to be entered in a particular format, such as a date.

In the example below, the user is expected to provide an expiry date. The input is checked when the user leaves the form field, for example, by using the tab key to move the focus to the next field or by clicking on another field.

###### 예제

#ex4 div {margin-bottom:.75em;}

Expiry date:

inputs = document.querySelectorAll('#ex4 input'); for (var i = inputs.length - 1; i >= 0; i--) { inputs\[i\].addEventListener('blur', function(event){ function setError(el, msg) { el.parentNode.querySelector('strong').innerHTML = "Error:"; el.parentNode.className='error'; el.parentNode.querySelector('span').innerHTML = msg; } function setSuccess(el) { el.parentNode.querySelector('strong').innerHTML = "OK:"; el.parentNode.className='success'; el.parentNode.querySelector('span').innerHTML = "&check;"; } if (this.id == 'expire5') { if (this.value.match(new RegExp('\[0-9\]{2}\\/\[0-9\]{4}'))) { setSuccess(this); } else { setError(this, 'Use the format MM/YYYY.'); } } else if (this.id == 'username5') { if (taken_usernames.includes(this.value.trim()) == false) { setSuccess(this); } else { setError(this, 'Username already taken.'); } } event.preventDefault(); return false; }); };

###### 코드 스니펫

```
<div>
	<label for="expire"><strong></strong> Expiry date:</label>
	<input type="text" name="expire" id="expire" value="03.2015" aria-describedby="expDesc3">
	<span id="expDesc3" aria-live="assertive"></span>
</div>
```

Note

The displayed message in this example is coded using a `<span>` element that has an `aria-live` attribute with the value `assertive`. The contents of this so called “live region” is conveyed to screen readers and other assistive technology. The value “assertive” emphasizes the importance of the message and causes screen readers to interrupt their current tasks to read aloud this message. Thus the message is read aloud before the next element that received the focus is announced to the user.

# Multi-page Forms

in [Forms Tutorial](https://www.w3.org/WAI/tutorials/forms/)

## Overview

Where possible, divide long forms into multiple smaller forms that constitute a series of logical steps or stages. This helps make long forms less daunting and easier to understand, particularly for people who are less experienced using computers or who have various cognitive disabilities.

Page Contents

- [Indicating progress](#indicating-progress)
  - [Using the page title](#using-the-page-title)
  - [Using the main heading](#using-the-main-heading)
  - [Using the HTML5 progress element](#using-the-html5-progress-element)
  - [Using step-by-step indicator](#using-step-by-step-indicator)

The following basic principles should apply for multi-step forms:

- Repeat [overall instructions](https://www.w3.org/WAI/tutorials/forms/instructions/#overall-instructions) on every page.
- Split the form up according to its logical groups of controls. For example, in an online shop, shipping and payment information are typically separated.
- Make it easy to recognize and to skip optional stages. For example, highlight optional steps in the main heading of the web page and provide an option to skip.
- If possible, don’t set a time limit to fill out the form. If a time limit is required, provide a feature that allows the user to adjust or extend the time limit.

## Indicating progress

If possible, the first step of a form should explain how many steps will follow. Each step should inform the user about the progress they are making.

### Using the page title

The `<title>` element is the first item read by many people, such as screen reader users. Changing the title of the page to include the progress gives immediate feedback. This information should precede other information provided in the title, such as the name of the step or any error notifications.

###### 예제

Step 2 of 4: Shipping Address – Complete Purchase – Galactic Teddy Bears Shop

Code

```
<title>Step 2 of 4: Shipping Address – Complete Purchase – Galactic Teddy Bears Shop</title>
```

### Using the main heading

Using the main heading to inform users is a good way to provide the same information for people scanning the page visually, as the main heading usually is prominent in the document.

###### 예제

# Shipping Address (Step 2 of 4)

Code

```
<h1>Shipping Address (Step 2 of 4)</h1>
```

### Using the HTML5 progress element

HTML5 provides a `progress` element that can be used to inform users about the progress. This can be particularly useful in situations where the number of steps depends on user input, such as in a survey where steps are skipped depending on how questions were answered.

###### 예제

Survey (Step 1 of circa 7)

Survey (Step 2 of circa 7)

\[…\]

Survey (Step 6 of circa 7)

Survey (Finished)

progress { color: #036; font-size: .6em; line-height: 1.5em; text-indent: .5em; width: 15em; height: 1em; border: 1px solid #036; border-radius: 1em; background: #fff; overflow:hidden; } progress::-webkit-progress-bar { background-color:#FFF; } progress::-webkit-progress-value { background-color: #036; } progress::-moz-progress-bar { background-color:#036; }

Code

```
Survey <progress max="7" value="1">(Step 1 of circa 7)</progress><br>

Survey <progress max="7" value="2">(Step 2 of circa 7)</progress><br>

[…]

Survey <progress max="7" value="6">(Step 6 of circa 7)</progress><br>

Survey <progress max="7" value="7">(Finished)</progress>
```

The progress element, like other form elements, is a component from the operating system rendered directly on the website. Those components are animated in some operating systems which would violate WCAG’s [2.2.2 Pause, Stop, Hide](https://www.w3.org/WAI/WCAG21/quickref/#pause-stop-hide) success criterion that requires that users are able to disable an animation that starts automatically, lasts more than 5 seconds and is presented in parallel with other content.

The animation can be stopped by using custom styling with browser-specific CSS as shown below.

Code

```
/* Microsoft IE */
progress {
  color: #036;
}

/* Apple Safari and Google Chrome */
progress::-webkit-progress-bar {
	background-color: #FFF;
}
progress::-webkit-progress-value {
	background-color: #036;
}

/* Mozilla Firefox */
progress::-moz-progress-bar {
	background-color: #036;
}
```

### Using step-by-step indicator

If a form has a known number of steps to be completed, a step-by-step indicator can help users orient themselves. In the example below, we use an ordered list with a list item for every step. Visually hidden text is used to indicate the current and completed steps. If possible, provide a link to steps already completed, so the user can review them. In this case, any data already entered in the current step should be saved.

###### 예제

1.  Completed: [Billing Address](billing.html)
2.  Current: Shipping Address
3.  Review Order
4.  Payment
5.  Finish Purchase

.tlwrapper { display:table; width: 100%; } .timeline { display: table-row; counter-reset: timeline; } .timeline li { display: table-cell; width: 20%; counter-increment: timeline; list-style: none; text-align: center; padding: .25em .5em; overflow:hidden; position: relative; background-color: #fff; padding-left: 25px; white-space: nowrap; } .timeline li:first-child { padding-left: 0; } .timeline li:after { left: 0; top: 50%; border: solid transparent; content: " "; height: 0; width: 0; position: absolute; pointer-events: none; border-color: rgba(151, 204, 237, 0); border-left-color: #ccc; border-width: 20px; margin-top: -20px; } .timeline li:first-child:after { display: none; } .timeline li a, .timeline li > span { z-index: 100; position: relative; display: block; color: #555; } .timeline li a:before, .timeline li > span:before { display: inline-block; color: #555; content: counter(timeline); background-color: none; border: 3px solid #555; margin-right:.25em; border-radius: 5px; padding: 0 .25em; } .timeline li.timeline-current > span, .timeline li.timeline-current a { color: #036; font-weight: bold; } .timeline li.timeline-current > span:before { color: #fff; background-color: #036; border-color: #036; } .timeline li.timeline-past { background-color: #ccc; } .timeline li.timeline-past a:before { color: green; content: "\\2713"; background-color: #fff; border-color: green; } .timeline li.timeline-past a:hover:before, .timeline li.timeline-past a:focus:before { background-color: green; color: #fff; }

Code 'HTML

```
<div class="tlwrapper">
	<ol class="timeline">
		<li class="timeline-past">
				<span class="visuallyhidden">Completed: </span>
				<a href="billing.html">Billing Address</a>
		</li>
		<li class="timeline-current">
			<span class="visuallyhidden">Current: </span>
			<span>Shipping Address</span>
		</li>
		<li><span>Review Order</span></li>
		<li><span>Payment</span></li>
		<li><span>Finish Purchase</span></li>
	</ol>
</div>
```

# Custom Controls

in [Forms Tutorial](https://www.w3.org/WAI/tutorials/forms/)

## Overview

Sometimes form designs require something beyond what is achievable with standard form controls. In such cases, it is possible to build additional functionality and styling to standard controls. To ensure robustness, try to reuse HTML elements that do a subset of the functionality that the final control is intended to cover, and build from there. The following examples provide some general guidance on what to consider to ensure the additions are made accessible.

For components where there is no adequate HTML element to build on, WAI-ARIA attributes can be useful to convey the functionality for people using assistive technologies.

Page Contents

- [A Share Button](#a-share-button)
- [A Star Rating](#a-star-rating)

## A Share Button

The example below shows a social media “share button” that has two functions: it shows how many people have already activated the button (“shared”), and allows users to press the button to activate the share function.

The custom button relies on CSS to style a regular `<button>` element so that the basic functionality remains intact when it is rendered without CSS. For example, most screen readers will announce the button and its contents.

Also, the `action` attribute of the `<form>` element references a server-side script that carries out the same functionality for cases when JavaScript is not supported.

###### 예제

3  Shares

#share-btn { line-height: 1; float:none; } #share-btn\[disabled\] { background: #063; border: 1px solid #063; } #share-btn\[disabled\]:hover, #share-btn\[disabled\]:focus { text-decoration: none; } #share-btn\[disabled\] .count { color: #063; } #share-btn .count { background-color: #fff; color: #036; min-width: 1em; line-height: 1; display: inline-block; border-radius: 50px; border: 4px solid #fff; text-align: center; } document.getElementById('share-btn').removeAttribute('disabled'); document.getElementById('share-btn').addEventListener('click', function(event){ event.preventDefault(); event.stopImmediatePropagation(); var count = this.querySelector('.count'); var text = this.querySelector('.text'); count.textContent = parseInt(count.textContent) + 1; text.textContent = "Shared ✓"; this.setAttribute("disabled", "true"); });

Code: HTML

```
<form action="path/to/submit">
	<button type="submit" id="share-btn" class="btn-primary">
		<span class="count">3</span>
		<span class="text">Shares</span>
	</button>
</form>
```

Code: JavaScript

```
document.getElementById('share-btn').addEventListener('click', function(event){
	event.preventDefault();
	event.stopImmediatePropagation();

	var count = this.querySelector('.count');
	var text = this.querySelector('.text');

	count.textContent = parseInt(count.textContent) + 1;
	text.textContent = "Shared ✓";

	this.setAttribute("disabled", "true");
});
```

## A Star Rating

A star rating usually consists of images of five stars that can be used to rate a particular item. A mouse user hovers over the stars and clicks one to select it. For example, if the user clicks on the third star from the left, the rating of the item is 3 of 5 stars.

To make this as accessible as possible, a form is used with its fields visually hidden. It contains six radio buttons, one for each star and another for 0 stars, which is checked by default. The labels for the radio buttons contain actual text (“1 Star”, “2 Stars”, …), and are also hidden visually. The form also contains a visually hidden submit button so that the form is not automatically submitted when keyboard users browse through the radio buttons.

The images of the stars are generated using SVG. The coloring animation of these stars is initiated through the CSS `:focus` and `:hover` pseudo-classes so that they can be activated using a mouse, keyboard, and other input methods. The `:checked` pseudo-class and the general sibling selector `~` are used to indicate the selected, active, and inactive stars.

###### 예제

0 Stars 1 Star 2 Stars 3 Stars 4 Stars 5 Stars Submit rating

#star_rating svg { width: 1em; height: 1em; fill: currentColor; stroke: currentColor; } #star_rating label, #star_rating output { display:block; float:left; font-size: 2em; height: 1.2em; color: #036; cursor: pointer; border-bottom: 2px solid transparent; } #star_rating output { font-size: 1.5em; padding: 0 1em; } #star_rating input:checked ~ label { color: #858585; } #star_rating input:checked + label { color: #036; border-bottom-color: #036; } #star_rating input:focus + label { border-bottom-style: dotted; } #star_rating:hover input + label { color: #036; } #star_rating input:hover ~ label, #star_rating input:focus ~ label, #star_rating input\[id="star0"\] + label { color: #999; } #star_rating input:hover + label, #star_rating input:focus + label { color: #036; } #star_rating input\[id="star0"\]:checked + label { color: #ff2d21; } #star_rating \[type="submit"\] { float: none; } var radios = document.querySelectorAll('#star_rating input\[type=radio\]'); var btn = document.querySelector('#star_rating button'); var output = document.querySelector('#star_rating output'); var do_something = function(stars) { // An AJAX request could send the data to the server output.textContent = stars; }; Array.prototype.forEach.call(radios, function(el, i){ var label = el.nextSibling.nextSibling; label.addEventListener("click", function(event){ do_something(label.querySelector('span').textContent); }); }); document.querySelector('#star_rating').addEventListener('submit', function(event){ do_something(document.querySelector('#star_rating :checked ~ label span').textContent); event.preventDefault(); event.stopImmediatePropagation(); });

Code: HTML

```
<form action="#" id="star_rating">
 <input value="0" id="star0" checked
	type="radio" name="rating" class="visuallyhidden">
	<label for="star0">
		<span class="visuallyhidden">0 Stars</span>
		<svg viewBox="0 0 512 512">
			<g stroke-width="70" stroke-linecap="square">
				<path d="M91.5,442.5 L409.366489,124.633512"></path>
				<path d="M90.9861965,124.986197 L409.184248,443.184248"></path>
			</g>
		</svg>
	</label>

	<input value="1" id="star1"
		type="radio" name="rating" class="visuallyhidden">
	<label for="star1">
		<span class="visuallyhidden">1 Star</span>
		<svg viewBox="0 0 512 512"><path d="M512 198.525l-176.89-25.704-79.11-160.291-79.108 160.291-176.892 25.704 128 124.769-30.216 176.176 158.216-83.179 158.216 83.179-30.217-176.176 128.001-124.769z"></path></svg>
	</label>

	<input value="2" id="star2"
		type="radio" name="rating" class="visuallyhidden">
	<label for="star2">
		<span class="visuallyhidden">2 Stars</span>
		<svg viewBox="0 0 512 512">…</svg>
	</label>

	<input value="3" id="star3"
		type="radio" name="rating" class="visuallyhidden">
	<label for="star3">
		<span class="visuallyhidden">3 Stars</span>
		<svg viewBox="0 0 512 512">…</svg>
	</label>

	<input value="4" id="star4"
		type="radio" name="rating" class="visuallyhidden">
	<label for="star4">
		<span class="visuallyhidden">4 Stars</span>
		<svg viewBox="0 0 512 512">…</svg>
	</label>

	<input value="5" id="star5"
		type="radio" name="rating" class="visuallyhidden">
	<label for="star5">
		<span class="visuallyhidden">5 Stars</span>
		<svg viewBox="0 0 512 512">…</svg>
	</label>

	<button type="submit" class="btn-small visuallyhidden focusable">Submit rating</button>

	<output></output>
</form>
```

Code: CSS

```
#star_rating svg {
	width: 1em;
	height: 1em;
	fill: currentColor;
	stroke: currentColor;
}
#star_rating label, #star_rating output {
	display: block;
	float: left;
	font-size: 2em;
	height: 1.2em;
	color: #036;
	cursor: pointer;
	/* Transparent border-bottom avoids jumping
	   when a colored border is applied
		 on :hover/:focus */
	border-bottom: 2px solid transparent;
}
#star_rating output {
	font-size: 1.5em;
	padding: 0 1em;
}
#star_rating input:checked ~ label {
	color: #999;
}
#star_rating input:checked + label {
	color: #036;
	border-bottom-color: #036;
}
#star_rating input:focus + label {
	border-bottom-style: dotted;
}
#star_rating:hover input + label {
	color: #036;
}
#star_rating input:hover ~ label,
#star_rating input:focus ~ label,
#star_rating input[id="star0"] + label {
	color: #999;
}
#star_rating input:hover + label,
#star_rating input:focus + label {
	color: #036;
}
#star_rating input[id="star0"]:checked + label {
	color: #ff2d21;
}
#star_rating [type="submit"] {
	float: none;
}
```

Code: JavaScript

```
var radios = document.querySelectorAll('#star_rating input[type=radio]');
var output = document.querySelector('#star_rating output');

var do_something = function(stars) {
	// An AJAX request could send the data to the server
	output.textContent = stars;
};

// Iterate through all radio buttons and add a click
// event listener to the labels
Array.prototype.forEach.call(radios, function(el, i){
	var label = el.nextSibling.nextSibling;
	label.addEventListener("click", function(event){
		do_something(label.querySelector('span').textContent);
	});
});

// If the form gets submitted, do_something
document.querySelector('#star_rating').addEventListener('submit', function(event){
	do_something(document.querySelector('#star_rating :checked ~ label span').textContent);
	event.preventDefault();
	event.stopImmediatePropagation();
});
```

- [Previous: Multi-page Forms](https://www.w3.org/WAI/tutorials/forms/multi-page/)
