# 애니메이션 기본

animejs, snapjs, vivusjs 등 여러 쓰기 편한 SVG 애니메이션 라이브러리가 있지만 <br>
기본적으로 원리를 이해하고 사용하는게 중요합니다. <br>
path 속성을 통해 그린 라인을 애니메이션을 통해 움직여 보겠습니다.

<br>

### path

```html
<svg width="300" height="300" id="line">
	<path d="M10 10 L 290 290" stroke="black" stroke-width="5"></path>
</svg>
```
![1](https://user-images.githubusercontent.com/7742074/122415351-cd4e5500-cfc2-11eb-8fba-0c5a3b192e1f.gif)

첫 모양입니다. <br>
10,10 위치에서 시작하여 290,290 위치에서 끝나는 라인을 그립니다. <br>
애니메이션에는 strokeDasharray, strokeDashoffset 속성을 사용합니다.

<br>

### strokeDasharray, strokeDashoffset
```html
<svg width="300" height="300" id="line">
	<path d="M10 10 L 290 290" stroke="black" stroke-width="5" stroke-dasharray="100 20" stroke-dashoffset="30"></path>
</svg>
```

![4](https://user-images.githubusercontent.com/7742074/122416029-5bc2d680-cfc3-11eb-981c-64fac05f5ee4.gif)

strokeDasharray는 점선을 그리고, <br>
strokeDashoffset는 시작점의 위치를 당깁니다.<br>
이 시작점 위치를 조절하여 라인이 그려지는 효과를 보여줍니다.

<br>

### animate

```html
(function($){
	var line = $('#line').find('path')[0];
	var lineLength = line.getTotalLength();

	line.style.strokeDasharray = lineLength; // 점선 형태로 모양 찍기
	line.style.strokeDashoffset = lineLength; // 시작점 지정

	$('path').animate({
		'strokeDashoffset' : 0
	},1000);

})(jQuery);
```
![5](https://user-images.githubusercontent.com/7742074/122417633-96793e80-cfc4-11eb-868d-61c630196975.gif)

점섬 형태로 모양을 바꾸고, 시작점을 길이만큼 당깁니다.<br>
시작화면에서는 아무것도 보이지 않습니다. <br>
animate문의 실행되면 시작점이 0 위치로 애니메이션 됩니다.

<br>

## 글자 예제

```html
<svg width="1000" height="500" id="test">
	<path style="fill:none;stroke:#000000;stroke-width:2;stroke-miterlimit:10;" d="M193.952,72.806h17.34V45.059h-6.935
				c-2.314,0-3.469-1.156-3.469-3.47c0-2.312,1.154-3.469,3.469-3.469h10.405c2.312,0,3.468,1.156,3.468,3.469v34.684
				c0,2.313-1.156,3.47-3.468,3.47h-20.811c-4.801,0-8.89-1.69-12.27-5.072c-3.382-3.38-5.072-7.471-5.072-12.27V27.717
				c0-4.801,1.69-8.89,5.072-12.271c3.38-3.382,7.469-5.072,12.27-5.072h20.811c2.312,0,3.468,1.156,3.468,3.468
				c0,2.314-1.156,3.47-3.468,3.47h-20.811c-2.909,0-5.369,1.016-7.384,3.047c-2.015,2.032-3.022,4.484-3.022,7.357V62.4
				c0,2.908,1.008,5.368,3.022,7.382C188.583,71.797,191.043,72.806,193.952,72.806z"/>
</svg>
```

```javascript
(function ($) {
    var pathes = $('#test').find('path');
    pathes.each(function (i, path) {
        var total_length = path.getTotalLength();
        path.style.strokeDasharray = total_length + " " + total_length;
        path.style.strokeDashoffset = total_length;
        $(path).animate({
            "strokeDashoffset": 0
        }, 1500);
    });
})(jQuery);
```
![1](https://user-images.githubusercontent.com/7742074/123112908-1433c300-d479-11eb-8218-5eaeb034e94f.gif)


일러스트를 통해 문자를 그리고 SVG 형태로 소스를 뽑았습니다.<br>
그런 뒤 이전에 햇던 stroke 속성들을 적용하여 글자가 그려지는 이펙트를 그렸습니다.

<br>

## 버튼 예제

```html
<div class="svg-wrapper">
	<svg height="60" width="320" xmlns="http://www.w3.org/2000/svg">
		<rect class="shape" height="60" width="320" />
	</svg>
	<div class="text">HOVER</div>
</div>
```

```css
		html, body {
			background: #333;
			height: 100%;
			overflow: hidden;
			text-align: center;
		}
		.svg-wrapper {
			height: 60px;
			margin: 0 auto;
			position: relative;
			top: 50%;
			transform: translateY(-50%);
			width: 320px;
		}
		.shape {
			fill: transparent;
			stroke-dasharray: 140 540;
			stroke-dashoffset: -474;
			stroke-width: 8px;
			stroke: #19f6e8;
		}
		.text {
			color: #fff;
			font-family: 'Roboto Condensed';
			font-size: 22px;
			letter-spacing: 8px;
			line-height: 32px;
			position: relative;
			top: -48px;
		}
		@keyframes draw {
			0% {
				stroke-dasharray: 140 540;
				stroke-dashoffset: -474;
				stroke-width: 8px;
			}
			100% {
				stroke-dasharray: 760;
				stroke-dashoffset: 0;
				stroke-width: 2px;
			}
		}
		.svg-wrapper:hover .shape {
			-webkit-animation: 0.5s draw linear forwards;
			animation: 0.5s draw linear forwards;
		}
```

![1](https://user-images.githubusercontent.com/7742074/123282997-ec5e6100-d545-11eb-84d9-cb839a39a014.gif)

글자 애니메이션과 마찬가지로 stroke 속성을 활용하여 <br>
버튼의 테두리에 효과를 줄 수 있습니다.


### 애니메이션 라이브러리

<a target="_blank" href="https://github.com/juliangarnier/anime">Anime.js</a><br>
<a target="_blank" href="https://github.com/adobe-webplatform/Snap.svg">Snap.svg</a><br>
<a target="_blank" href="https://github.com/maxwellito/vivus">Vivus</a><br>
<a target="_blank" href="https://github.com/ConnorAtherton/walkway">Walkway</a><br>
<a target="_blank" href="https://github.com/camoconnell/lazy-line-painter">Lazy line painter</a>