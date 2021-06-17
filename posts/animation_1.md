# 애니메이션 기본

animejs, snapjs, vivusjs 등 여러 쓰기 편한 SVG 애니메이션 라이브러리가 있지만
기본적으로 원리를 이해하고 사용하는게 중요합니다.
path 속성을 통해 그린 라인을 애니메이션을 통해 움직여 보겠습니다.

<br>

### path

```html
<svg width="300" height="300" id="line">
	<path d="M10 10 L 290 290" stroke="black" stroke-width="5"></path>
</svg>
```
![1](https://user-images.githubusercontent.com/7742074/122415351-cd4e5500-cfc2-11eb-8fba-0c5a3b192e1f.gif)

첫 모양입니다.
10,10 위치에서 시작하여 290,290 위치에서 끝나는 라인을 그립니다.
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
strokeDashoffset는 시작점의 위치를 당깁니다.
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

점섬 형태로 모양을 바꾸고, 시작점을 길이만큼 당깁니다.
시작화면에서는 아무것도 보이지 않습니다.
animate문의 실행되면 시작점이 0 위치로 애니메이션 됩니다.

<br>

### 애니메이션 라이브러리

<a target="_blank" href="https://github.com/juliangarnier/anime">Anime.js</a><br>
<a target="_blank" href="https://github.com/adobe-webplatform/Snap.svg">Snap.svg</a><br>
<a target="_blank" href="https://github.com/maxwellito/vivus">Vivus</a><br>
<a target="_blank" href="https://github.com/ConnorAtherton/walkway">Walkway</a><br>
<a target="_blank" href="https://github.com/camoconnell/lazy-line-painter">Lazy line painter</a>