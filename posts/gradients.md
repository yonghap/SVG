# 그라디언트 (Gradients)

그라이언트의 종류에는 선형과 방사형이 있습니다. <br>
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

## 방사형 그라디언트

```html
<?xml version="1.0" standalone="no"?>
<svg width="120" height="240" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <radialGradient id="RadialGradient1">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
        <radialGradient id="RadialGradient2" cx="0.25" cy="0.25" r="0.25">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
    </defs>
    <rect x="10" y="10" rx="15" ry="15" width="100" height="100" fill="url(#RadialGradient1)"/>
    <rect x="10" y="120" rx="15" ry="15" width="100" height="100" fill="url(#RadialGradient2)"/>
</svg>
```

![gradient](https://developer.mozilla.org/files/726/SVG_Radial_Gradient_Example.png)

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients</sub>

<br>

## 중심 및 초점

그라디언트의 중심과 초점을 조절할 수 있습니다.

```html
<?xml version="1.0" standalone="no"?>
<svg width="120" height="120" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <radialGradient id="Gradient"
            cx="0.5" cy="0.5" r="0.5" fx="0.25" fy="0.25">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
    </defs>

    <rect x="10" y="10" rx="15" ry="15" width="100" height="100"
    fill="url(#Gradient)" stroke="black" stroke-width="2"/>
    
    <circle cx="60" cy="60" r="50" fill="transparent" stroke="white" stroke-width="2"/>
    <circle cx="35" cy="35" r="2" fill="white" stroke="white"/>
    <circle cx="60" cy="60" r="2" fill="white" stroke="white"/>
    <text x="38" y="40" fill="white" font-family="sans-serif" font-size="10pt">(fx,fy)</text>
    <text x="63" y="63" fill="white" font-family="sans-serif" font-size="10pt">(cx,cy)</text>
</svg>
```

![gradient](https://developer.mozilla.org/files/727/SVG_Radial_Grandient_Focus_Example.png)

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients</sub>

<br>

## spreadMethod

그라이언트가 원 외부로 이동할 경우 어떻게 처리할지를 정의합니다.

```html
<?xml version="1.0" standalone="no"?>
<svg width="220" height="220" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <radialGradient id="GradientPad"
            cx="0.5" cy="0.5" r="0.4" fx="0.75" fy="0.75"
            spreadMethod="pad">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
        <radialGradient id="GradientRepeat"
            cx="0.5" cy="0.5" r="0.4" fx="0.75" fy="0.75"
            spreadMethod="repeat">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
        <radialGradient id="GradientReflect"
            cx="0.5" cy="0.5" r="0.4" fx="0.75" fy="0.75"
            spreadMethod="reflect">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
    </defs>
    <rect x="10" y="10" rx="15" ry="15" width="100" height="100" fill="url(#GradientPad)"/>
    <rect x="10" y="120" rx="15" ry="15" width="100" height="100" fill="url(#GradientRepeat)"/>
    <rect x="120" y="120" rx="15" ry="15" width="100" height="100" fill="url(#GradientReflect)"/>

    <text x="15" y="30" fill="white" font-family="sans-serif" font-size="12pt">Pad</text>
    <text x="15" y="140" fill="white" font-family="sans-serif" font-size="12pt">Repeat</text>
    <text x="125" y="140" fill="white" font-family="sans-serif" font-size="12pt">Reflect</text>
</svg>
```

![gradient](https://developer.mozilla.org/files/728/SVG_SpreadMethod_Example.png)

<sub>* https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients</sub>

<br>

## gradientunits

그라디언트가 표시될 좌표를 정의합니다.

### gradientUnits="objectBoundingBox"

```html
<svg height="100%" width="100%" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <linearGradient gradientUnits="objectBoundingBox" id="myid" x1="0%" x2="100%" y1="0%" y2="0%">
            <stop/>
            <stop offset="50%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </linearGradient>
    </defs>
    <circle cx="0%" cy="0%" fill="url(#myid)" r="50vh"/>
    <circle cx="50%" cy="50%" fill="url(#myid)" r="50vh"/>
    <circle cx="100%" cy="100%" fill="url(#myid)" r="50vh"/>
</svg>
```

![gradient](https://user-images.githubusercontent.com/7742074/120206917-bd1a4400-c266-11eb-815c-7cc890140375.jpg)

```html
<svg height="100%" width="100%" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <radialGradient cx="50%" cy="50%" fr="0%" fx="50%" fy="50%" gradientUnits="objectBoundingBox" id="myid" r="50%">
            <stop/>
            <stop offset="50%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
    </defs>
    <circle cx="0%" cy="0%" fill="url(#myid)" r="50vh"/>
    <circle cx="50%" cy="50%" fill="url(#myid)" r="50vh"/>
    <circle cx="100%" cy="100%" fill="url(#myid)" r="50vh"/>
</svg>
```

![gradient](https://user-images.githubusercontent.com/7742074/120206911-bbe91700-c266-11eb-9689-d2c2cb491c36.jpg)

<br>

### gradientUnits="userSpaceOnUse"

```html
<svg height="100%" width="100%" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <linearGradient gradientUnits="userSpaceOnUse" id="myid" x1="0%" x2="100%" y1="0%" y2="0%">
            <stop/>
            <stop offset="50%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </linearGradient>
    </defs>
    <circle cx="0%" cy="0%" fill="url(#myid)" r="50vh"/>
    <circle cx="50%" cy="50%" fill="url(#myid)" r="50vh"/>
    <circle cx="100%" cy="100%" fill="url(#myid)" r="50vh"/>
</svg>
```

![gradient](https://user-images.githubusercontent.com/7742074/120206921-bd1a4400-c266-11eb-9eed-2331ada6a99b.jpg)



```html
<svg height="100%" width="100%" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <radialGradient cx="50%" cy="50%" fr="0%" fx="50%" fy="50%" gradientUnits="userSpaceOnUse" id="myid" r="50%">
            <stop/>
            <stop offset="50%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
    </defs>
    <circle cx="0%" cy="0%" fill="url(#myid)" r="50vh"/>
    <circle cx="50%" cy="50%" fill="url(#myid)" r="50vh"/>
    <circle cx="100%" cy="100%" fill="url(#myid)" r="50vh"/>
</svg>
```

![gradient](https://user-images.githubusercontent.com/7742074/120206915-bc81ad80-c266-11eb-9eae-260deb605ca8.jpg)

<sub>* https://osbo.com/svg/attributes/gradientunits/</sub>

<br>