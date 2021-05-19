# 도형 (Shape)

SVG의 기본 도형입니다.

<br>

```html
<svg width="200" height="250" version="1.0">
	<!-- Rect -->
	<rect x="10" y="10" width="30" height="30" stroke="black" fill="transparent" stroke-width="5" />
	<rect x="60" y="10" rx="10" ry="10" width="30" height="30" stroke="black" fill="transparent" stroke-width="5"/>

	<!-- Circle -->
	<circle cx="25" cy="75" r="20" stroke="red" fill="transparent" stroke-width="5" />
	<ellipse cx="75" cy="75" rx="20" ry="5" stroke="red" fill="transparent" stroke-width="5"/>

	<!-- Line -->
	<line x1="10" x2="50" y1="110" y2="150" stroke="orange" stroke-width="5" />
	<polyline points="60 110 65 120 70 115 75 130 80 125 85 140 90 135 95 150 100 145"
	          stroke="orange" fill="transparent" stroke-width="5"/>

	<polygon points="50 160 55 180 70 180 60 190 65 205 50 195 35 205 40 190 30 180 45 180"
	         stroke="green" fill="transparent" stroke-width="5"/>
	<path d="M20,230 Q40,205 50,230 T90,230" fill="none" stroke="blue" stroke-width="5"/>
</svg>
```
![shape](https://developer.mozilla.org/@api/deki/files/359/=Shapes.png)

<sub>* https://developer.mozilla.org/ko/docs/Web/SVG/Tutorial/Basic_Shapes </sub>

<br>

## Rect

> **x** : 사각형 좌측 상단의 x값 <br>
> **y** : 사각형 좌측 상단의 y값 <br>
> **width** : 사각형 넓이 <br>
> **height** : 사각형 높이 <br>
> **rx** : x 방향 모서리의 반지름 <br>
> **ry** : y 방향 모서리의 반지름 <br>

<br>

## Circle

> **rx** : x 방향 반지름의 길이 <br>
> **ry** : y 방향 반지름의 길이 <br>
> **cx** : 원의 중심 x값 <br>
> **cy** : 원의 중심 y값 <br>

<br>

## Line

> **x1** : 점 1의 x값 <br>
> **y1** : 점 1의 y값 <br>
> **x2** : 점 2의 x값 <br>
> **y2** : 점 2의 y값 <br>

<br>

## Polyline

> **x1 y1, x2 y2, x3 y3...** : 좌표들

Polyline은 선이 길어질 수 있으므로 속성 하나에 모든 좌표를 표시합니다.

<br>

## Polygon

> **x1 y1, x2 y2, x3 y3...** : 좌표들

Polygon은 처음 좌표와 마지막 좌표를 이어 도형을 만듭니다.

<br>

## Path

Path는 SVG에서 사용하는 가장 일반적인 속성이며 Polygon처럼 단일 속성으로 표시합니다. <br>
여러가지 복잡한 도형을 그릴 수 있습니다.