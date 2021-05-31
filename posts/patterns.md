# 패턴 (Patterns)

패턴은 SVG에서 사용하는 칠하기 종류중 하나입니다. <br>
SVG뿐만 아니라 다양한 그래픽 툴에서도 사용합니다. <br>
그라디언트와 마찬가지로 defs 섹션에 따로 정의합니다.


<br><br>

```html
<svg width="200" height="200" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <linearGradient id="Gradient1">
            <stop offset="5%" stop-color="white"/>
            <stop offset="95%" stop-color="blue"/>
        </linearGradient>
        <linearGradient id="Gradient2" x1="0" x2="0" y1="0" y2="1">
            <stop offset="5%" stop-color="red"/>
            <stop offset="95%" stop-color="orange"/>
       </linearGradient>
    
        <pattern id="Pattern" x="0" y="0" width=".25" height=".25">
            <rect x="0" y="0" width="50" height="50" fill="skyblue"/>
            <rect x="0" y="0" width="25" height="25" fill="url(#Gradient2)"/>
            <circle cx="25" cy="25" r="20" fill="url(#Gradient1)" fill-opacity="0.5"/>
        </pattern>
    </defs>
    
    <rect fill="url(#Pattern)" stroke="black" width="200" height="200"/>
</svg>
```

![gradient](https://developer.mozilla.org/files/725/SVG_Pattern_Example.png)

<sub>* https://developer.mozilla.org/ko/docs/Web/SVG/Tutorial/Patterns</sub>

<br>

패턴 요소 안에는 다른 기본 도형과 그라디언트 투명도 등을 줄 수 있습니다. <br>
패턴의 정의 되어 있는 width와 height의 크기의 값은 전체 넓이나 높이의 비율을 의미합니다. <br>
.25의 값이므로 패턴이 4번 반복됩니다.

<br>

## patternUnits, patternContentUnits

패턴을 채우는 방법을 정의합니다.


```html
<svg width="800px" height="800px">
	<defs>
		<pattern id="pattern1" x="0" y="0" width="0.2" height="0.2" patternUnits="objectBoundingBox"
		         patternContentUnits="userSpaceOnUse">
			<circle cx="10" cy="10" r="10" fill="blue"/>
		</pattern>

		<pattern id="pattern2" x="10" y="10" width="20" height="20" patternUnits="userSpaceOnUse"
		         patternContentUnits="objectBoundingBox">
			<circle cx=".1" cy=".1" r="0.1" fill="blue"/>
		</pattern>

		<pattern id="pattern3" x="10" y="10" width="20" height="20" patternUnits="userSpaceOnUse"
		         patternContentUnits="userSpaceOnUse">
			<circle cx="10" cy="10" r="10" fill="blue"/>
		</pattern>

		<pattern id="pattern4" x="0" y="0" width="0.2" height="0.2" patternUnits="objectBoundingBox"
		         patternContentUnits="objectBoundingBox">
			<circle cx=".1" cy=".1" r="0.1" fill="blue"/>
		</pattern>
	</defs>

	<rect x="10" y="10" width="100" height="100" stroke="black" fill="url(#pattern1)"/>
	<rect x="150" y="10" width="200" height="150" stroke="black" fill="url(#pattern1)"/>
	<text x="10" y="200">patternUnits="objectBoundingBox" (20% of shape)</text>
	<text x="10" y="220">patternContentUnits="userSpaceOnUse" (20px circle)</text>
	<text x="10" y="240" stroke="blue" stroke-width="1">(Units used by default)</text>

	<rect x="10" y="310" width="100" height="100" stroke="black" fill="url(#pattern3)"/>
	<rect x="150" y="310" width="200" height="150" stroke="black" fill="url(#pattern3)"/>
	<text x="10" y="500">patternUnits="userSpaceOnUse" (10px square box)</text>
	<text x="10" y="520">patternContentUnits="userSpaceOnUse" (20px circle)</text>

	<rect x="410" y="10" width="100" height="100" stroke="black" fill="url(#pattern2)"/>
	<rect x="550" y="10" width="200" height="150" stroke="black" fill="url(#pattern2)"/>
	<text x="410" y="200">patternUnits="userSpaceOnUse" (10px square box)</text>
	<text x="410" y="220">patternContentUnits="objectBoundingBox"(radius="10%")</text>

	<rect x="410" y="310" width="100" height="100" stroke="black" fill="url(#pattern4)"/>
	<rect x="550" y="310" width="200" height="150" stroke="black" fill="url(#pattern4)"/>
	<text x="410" y="500">patternUnits="objectBoundingBox" (20% of shape)</text>
	<text x="410" y="520">patternContentUnits="objectBoundingBox"(radius="10%")</text>

</svg>
```

![gradient](http://i.stack.imgur.com/k2t7Z.png)

<sub>* https://riptutorial.com/svg/example/19858/pattern-coverage-with-combinations-of-patternunits-and-patterncontentunits</sub>

