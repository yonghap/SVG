# 그라디언트 (Gradients)

그라이언트의 종류에는 선형과 방사형이 있습니다.
그라이언트는 모양을 정의하는 것이 아닌 재사용성을 위해 defs에 섹션에 따로 정의 합니다.

<br><br>

## 선형 그라디언트
```html
<svg width="120" height="240" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <linearGradient id="Gradient1">
            <stop class="stop1" offset="0%"/>
            <stop class="stop2" offset="50%"/>
           <stop class="stop3" offset="100%"/>
        </linearGradient>
        <linearGradient id="Gradient2" x1="0" x2="0" y1="0" y2="1">
            <stop offset="0%" stop-color="red"/>
            <stop offset="50%" stop-color="black" stop-opacity="0"/>
            <stop offset="100%" stop-color="blue"/>
        </linearGradient>
        <style type="text/css"><![CDATA[
            #rect1 { fill: url(#Gradient1); }
            .stop1 { stop-color: red; }
            .stop2 { stop-color: black; stop-opacity: 0; }
            .stop3 { stop-color: blue; }
        ]]></style>
    </defs>

    <rect id="rect1" x="10" y="10" rx="15" ry="15" width="100" height="100"/>
    <rect x="10" y="120" rx="15" ry="15" width="100" height="100" fill="url(#Gradient2)"/>
</svg>
```

![gradient](https://developer.mozilla.org/files/722/SVG_Linear_Gradient_Example.png)

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients</sub>

<br>

## 원형 그라디언트