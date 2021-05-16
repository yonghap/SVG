# Path

Path는 SVG에서 가장 많이 사용하고 가장 강력한 엘리먼트입니다.<br>
직선,곡선,호 등 다양한 형태를 그릴 수 있습니다.

<br><br>

## 선(Line) 명령어

### 직선

선 명령어는 두 점 사이를 잇는 역할을 합니다.<br>
M(Move to) 명령어로 시작할 위치를 지정합니다.

> **M x y** : 시작할 지점의 좌표 지정

```html
<path d="M10 10"/>
```

<br>

L(Line to) 명령어로 좌표를 찍고 선을 그립니다.

```html
<path d="M10 10 L 50 50" stroke="black" />
```


L 명령어로 직접 좌표를 찍어 선을 그릴 수도 있고<br>
H(horizontal), V(vertical) 명령어르 가로선이나 세로선을 그릴 수도 있습니다.

> **H x** : 가로선의 좌표 지정 <br>
> **V y** : 세로선의 좌표 지정

```html
<path d="M10 10 H 90 V 90 H 10 L 10 10"/>
```

위 예제는 M,H,V,L 명령어를 사용하여 사각형을 그립니다.<br><br>
Z(Close Path) 명령어로 패스를 닫습니다.<br>
마지막 좌표에서 시작 좌표로 직선을 그립니다.<br>
대문자 명령어는 절대적인 좌표를 의미하고 소문자 명령어는 상대적인 좌표를 의미합니다.

```html
<path d="M10 10 h 80 v 80 h -80 Z" fill="transparent" stroke="black"/>
```

![path](https://developer.mozilla.org/@api/deki/files/292/=Path_Line_Commands.png)

<br><br>

### 곡선

SVG의 곡선 명령어에는 3가지가 있습니다.<br>
베지어 곡선 2종류와 호를 활용한 곡선 1종류 입니다.<br><br>
3차 베지어 곡선은 두 개의 제어 좌표와 하나의 끝점을 가집니다.<br>
C(Cubic) 영령어를 사용합니다.

> **C x1 y1, x2 y2, x y** : 제어 좌표1, 제어 좌표1, 곡선의 끝 좌

```html
<svg width="190" height="160" xmlns="http://www.w3.org/2000/svg">
    <path d="M10 10 C 20 20, 40 20, 50 10" stroke="black" fill="transparent"/>
    <path d="M70 10 C 70 20, 120 20, 120 10" stroke="black" fill="transparent"/>
    <path d="M130 10 C 120 20, 180 20, 170 10" stroke="black" fill="transparent"/>
    <path d="M10 60 C 20 80, 40 80, 50 60" stroke="black" fill="transparent"/>
    <path d="M70 60 C 70 80, 110 80, 110 60" stroke="black" fill="transp표arent"/>
    <path d="M130 60 C 120 80, 180 80, 170 60" stroke="black" fill="transparent"/>
    <path d="M10 110 C 20 140, 40 140, 50 110" stroke="black" fill="transparent"/>
    <path d="M70 110 C 70 140, 110 140, 110 110" stroke="black" fill="transparent"/>
    <path d="M130 110 C 120 140, 180 140, 170 110" stroke="black" fill="transparent"/>
</svg>
```

아래와 같은 결과가 나옵니다.

![path](https://mdn.mozillademos.org/files/10401/Cubic_Bezier_Curves_with_grid.png)

<sub>* https://developer.mozilla.org/ko/docs/Web/SVG/Tutorial/Paths </sub>
