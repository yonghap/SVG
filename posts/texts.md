# 텍스트 (Texts)

SVG의 글꼴에는 두 가지 유형이 있습니다.
첫 번째는 이미지에 텍스트를 표현하는 것이고 두 번째는 SVG 글꼴입니다.

<br>

```html
<text x="10" y="10">Hello World!</text>
```

font-family, font-style, font-weight, font-variant, font-stretch, font-size,  <br>
font-size-adjust, kerning, letter-spacing, word-spacing와 text-decoration <br>
위 속성들은 속성이나 CSS 선언을 통해 설정할 수 있습니다.

<br>

## tspan

텍스트의 하위 요소를 표현하는데 사용합니다.
x,y 속성을 통해 절대 위치와 dx,dy 속성을 통해 상대 위치를 설정할 수 있습니다.

```html
<text>
    This is <tspan x="0" y="65" dx="10" dy="10"font-weight="bold" fill="red">bold and red</tspan>
</text>
```

<br>

## textPath

임의의 경로에 따라 텍스트를 정렬합니다.

```html
<path id="my_path" d="M 20,20 C 80,60 100,40 120,20" fill="transparent" />
<text>
    <textPath xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#my_path">
        A curve.
    </textPath>
</text>
```

![13](https://user-images.githubusercontent.com/7742074/120821790-bbb38900-c590-11eb-84bc-44228f636e5d.JPEG)

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Texts </sub>