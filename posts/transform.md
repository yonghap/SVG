# 기본 변형 (Basic Transformations)

svg 요소를 그룹핑하는 g 태그를 사용합니다.

```html
<svg width="30" height="10">
    <g fill="red">
        <rect x="0" y="0" width="10" height="10" />
        <rect x="20" y="0" width="10" height="10" />
    </g>
</svg>

```

<br>

## 위치 이동

```html
<svg width="40" height="50" style="background-color:#bff;">
    <rect x="0" y="0" width="10" height="10" transform="translate(30,40)" />
</svg>
```

두 번째 값이 없으면 0으로 간주합니다.

<br>

## 회전

```html
<svg width="31" height="31">
    <rect x="12" y="-10" width="20" height="20" transform="rotate(45)" />
</svg>
```

<br>

## 여러가지 변형

```html
<svg width="40" height="50" style="background-color:#bff;">
    <rect x="0" y="0" width="10" height="10" transform="translate(30,40) rotate(45)" />
</svg>
```

<br>

## 스케일

```html
<svg width="100" height="100">
    <g transform="scale(2)">
        <rect width="50" height="50" />
    </g>
</svg>
```

<br>

## SVG에 SVG 포함

```html
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="100" height="100">
    <svg width="100" height="100" viewBox="0 0 50 50">
        <rect width="50" height="50" />
    </svg>
</svg>
```

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Basic_Transformations </sub>