# Grid

SVG는 벡터 그래픽을 표현하기 위한 마크업 언어입니다. <br>
간단하게는 도형,아이콘부터 복잡하게는 애니메이션까지 다양한 분야의 벡터 그래픽을 <br>
웹상에 표현하게 해줍니다. <br>
SVG의 좌표는 웹 개발에서 많이 사용하는 좌표계를 사용합니다.

<br><br>

## default
```html
<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">
	
	<rect width="100%" height="100%" fill="red" />	
	
	<circle cx="150" cy="100" r="80" fill="green" />
	
	<text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>
</svg>
```

아래와 같은 결과가 나옵니다.

![1](https://user-images.githubusercontent.com/7742074/117831401-7b256000-b2af-11eb-8aaa-a303efa8a44a.gif)

<br><br>

## rect

```html
<rect x="0" y="0" width="100" height="100" />
```

![grid](https://developer.mozilla.org/@api/deki/files/78/=Canvas_default_grid.png)

<sub><sup>* https://developer.mozilla.org/ko/docs/Web/SVG/Tutorial/Positions </sup></sub>


0,0의 위치에서 100x100 크기의 사각형을 그립니다.

<br><br>

## width,height

```html
<svg width="100" height="100">
```

100x100px의 캔버스를 정의합니다.

<br><br>

```html
<svg width="200" height="200" viewBox="0 0 100 100">
```

svg의 사이즈는 200x200이지만 그 안에 0,0 위치에서 시작하는
100x100 크기의 상자를 확대하여 표시합니다.