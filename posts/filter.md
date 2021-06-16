# 필터 효과 (Filter Effect)

필터효과는 보다 정교한 효과를 만드는 SVG 매커니즘입니다.<br>
필터는 filter 요소 별로 정의되며 defs svg 파일의 섹션에 있어야 됩니다.


<br>

```html
<svg width="250" viewBox="0 0 200 85"
     xmlns="http://www.w3.org/2000/svg" version="1.1">
	<defs>
		<!-- Filter declaration -->
		<filter id="MyFilter" filterUnits="userSpaceOnUse"
		        x="0" y="0"
		        width="200" height="120">

			<!-- offsetBlur -->
			<feGaussianBlur in="SourceAlpha" stdDeviation="4" result="blur"/>
			<feOffset in="blur" dx="4" dy="4" result="offsetBlur"/>

			<!-- litPaint -->
			<feSpecularLighting in="blur" surfaceScale="5" specularConstant=".75"
			                    specularExponent="20" lighting-color="#bbbbbb"
			                    result="specOut">
				<fePointLight x="-5000" y="-10000" z="20000"/>
			</feSpecularLighting>
			<feComposite in="specOut" in2="SourceAlpha" operator="in" result="specOut"/>
			<feComposite in="SourceGraphic" in2="specOut" operator="arithmetic"
			             k1="0" k2="1" k3="1" k4="0" result="litPaint"/>

			<!-- merge offsetBlur + litPaint -->
			<feMerge>
				<feMergeNode in="offsetBlur"/>
				<feMergeNode in="litPaint"/>
			</feMerge>
		</filter>
	</defs>

	<!-- Graphic elements -->
	<g filter="url(#MyFilter)">
		<path fill="none" stroke="#D90000" stroke-width="10"
		      d="M50,66 c-50,0 -50,-60 0,-60 h100 c50,0 50,60 0,60z"/>
		<path fill="#D90000"
		      d="M60,56 c-30,0 -30,-40 0,-40 h80 c30,0 30,40 0,40z"/>
		<g fill="#FFFFFF" stroke="black" font-size="45" font-family="Verdana">
			<text x="52" y="52">SVG</text>
		</g>
	</g>
</svg>
```

![](https://user-images.githubusercontent.com/7742074/121897693-99bec100-cd5d-11eb-9c9c-91b8a26aaae2.jpg)

단계별로 확인해 보겠습니다.

<br>

### 1단계

```html
<feGaussianBlur in="SourceAlpha" stdDeviation="4" result="blur"/>
```

4의 흐림효과를 적용합니다. <br>
결과를 blur를 저장합니다.

<br>

### 2단계

```html
<feOffset in="blur"
          dx="4" dy="4"
          result="offsetBlur"/>
```

이전에 생성한 흐림효과를 가져오고 결과를 4, 4 이동합니다. <br>
결과를 offsetBlue에 저장합니다.

<br>

### 3단계

```html
<feSpecularLighting in="offsetBlur"
                    surfaceScale="5" specularConstant=".75"
                    specularExponent="20" lighting-color="#bbbbbb"
                    result="specOut">
    <fePointLight x="-5000" y="-10000" z="20000"/>
</feSpecularLighting>
```

offsetBlur를 가져와 조명효과를 생성하고 결과를 specOut에 저장합니다.

<br>

### 4단계

```html
<feComposite in="specOut" in2="SourceAlpha"
             operator="in"
             result="specOut"/>
```

specOut과 SourceAlpha를 가져와 specOut의 결과를 마스킹하여 결과가<br>
원본 SourceAlpha보다 크지 않도록 하고 specOut에 재정의합니다.

<br>

### 5단계

```html
<feComposite in="SourceGraphic" in2="specOut"
             operator="arithmetic"
             k1="0" k2="1" k3="1" k4="0"
             result="litPaint"/>
```

SourceGraphic와 specOut을 가져와 SourceGraphic 위에 specOut의 결과를 추가하고 <br>
litPaint에 저장합니다.

<br>

### 6단계

```html
<feMerge>
    <feMergeNode in="offsetBlur"/>
    <feMergeNode in="litPaint"/>
</feMerge>
```

offsetBlur와 조명 혀과가 있는 원본 소스 그래픽인 litPaint를 병합합니다.

<br>

### 단계별 결과

![](https://user-images.githubusercontent.com/7742074/121899015-f9699c00-cd5e-11eb-9cbb-8a6b1806398f.jpg)

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Filter_effects </sub>