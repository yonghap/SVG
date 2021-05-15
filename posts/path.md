# Path

Path는 SVG에서 가장 많이 사용하고 가장 강력한 엘리먼트입니다.
직선,곡선,호 등 다양한 형태를 그릴 수 있습니다.



## 선(Line) 명령어

선 명령어는 두 점 사이를 잇는 역할을 합니다.
M(Move to) 명령어로 시작할 위치를 지정합니다.

> **M x y** : 시작할 지점의 좌표 지정

```html
<path d="M10 10"/>
```

L(Line to) 명령어로 좌표를 찍고 선을 그립니다.

```html
<path d="M10 10 L 50 50" stroke="black" />
```

L 명령어로 직접 좌표를 찍어 선을 그릴 수도 있고
H(horizontal), V(vertical) 명령어르 가로선이나 세로선을 그릴 수도 있습니다.