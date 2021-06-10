# 클리핑과 마스킹 (Clipping and Masking)

SVG 모양의 일부를 제거하는 것은 클리핑입니다.<br>
마스킹은 여러 요소를 겹쳐서 모양을 만듭니다.

<br>

## 클립 만들기

```html
<svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <defs>
        <clipPath id="cut-off-bottom">
            <rect x="0" y="0" width="200" height="100" />
        </clipPath>
    </defs>
    
    <circle cx="100" cy="100" r="100" clip-path="url(#cut-off-bottom)" />
</svg>
```

![13](https://developer.mozilla.org/files/3224/clipdemo.png)

반지름 100짜리 원을 그립니다. <br>
clipPath 요소를 통해 칠해질 곳을 지정합니다. <br>
소스만 보면 clipPath 부분을 잘라내는 듯하지만, 해당 부분을 칠해지는 걸로 이해해야 합니다.

<br>

## 마스킹

```html
<svg width="200" height="200" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <defs>
        <linearGradient id="Gradient">
            <stop offset="0" stop-color="black" />
            <stop offset="1" stop-color="white" />
        </linearGradient>
        <mask id="Mask">
            <rect x="0" y="0" width="200" height="200" fill="url(#Gradient)"  />
        </mask>
    </defs>
    
    <rect x="0" y="0" width="200" height="200" fill="green" />
    <rect x="0" y="0" width="200" height="200" fill="red" mask="url(#Mask)" />
</svg>
```

![13](https://developer.mozilla.org/files/3234/maskdemo.png)

녹샌 레이어위에 빨간 레이어가 겹쳐져 있습니다.<br>
빨간 레이어는 흑백 그라데이션으로 채워진 rect 요소를 마스크로 가집니다.

<br>

## 전체 요소의 투명도 설정

```html
<rect x="0" y="0" width="100" height="100" opacity=".5" />
```
```html
<svg width="200" height="200" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <rect x="0" y="0" width="200" height="200" fill="blue" />
    <circle cx="100" cy="100" r="50" stroke="yellow" stroke-width="40" stroke-opacity=".5" fill="red" />
</svg>
```

![13](https://developer.mozilla.org/files/3231/opacitydemo.png)

파란색 배경에 빨간색 원이 표시됩니다.<br>
노란색 선은 50% 불투명도로 설정되어 표시됩니다.

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Clipping_and_masking </sub>