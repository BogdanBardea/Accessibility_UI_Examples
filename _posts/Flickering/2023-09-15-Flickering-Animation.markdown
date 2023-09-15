---
layout: post
title:  "Flickering Animation"
categories: jekyll update
---
## Description

<b>Flickering animations</b> refer to rapidly changing and alternating visual elements on a web page. When these animations persist, they pose a substantial accessibility challenge. These animations can manifest in various forms, including flashing banners, rotating carousels, or auto-playing videos with intense light effects.

## Instructions
Move the dot on the slider to set up the animation duration.

## Expectations

The box should complete an animation in the selected time.

## Example

<div>
<style>
.visually-hidden {
	/* https://github.com/twbs/bootstrap/blob/main/scss/mixins/_visually-hidden.scss */
	width: 1px !important;
	height: 1px !important;
	padding: 0 !important;
	margin: -1px !important;
	overflow: hidden !important;
	clip: rect(0, 0, 0, 0) !important;
	white-space: nowrap !important;
	border: 0 !important;
}
* {
	box-sizing: border-box;
}
body {
	background-color: var(--color-bg);
	/*font-family: sans-serif;
	line-height: 1.4;*/
	font: normal 400 100%/1.4 sans-serif;
	padding: env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left);
}
hr {
	border: 1px solid var(--color-border);
}
h1 {
	font-size: 125%;
}
	h1 span {}
h2 {
	font-size: 110%;
}
h3 {
	font-size: 100%;
}
a {
	color: var(--color-link);
}
.code {
	font-family: menlo, courier;
	font-size: .9em;
}
.example-box-wrapper {
	position: relative;
}
.example-box-wrapper > button {
	position: absolute;
	top: 0
	left: 0;
}
.example-box {
	width: 200px;
	height: 200px;
	background: linear-gradient(0deg,#3989b8 0%,rgba(36,97,149,1) 100%);
}
#example-01 {
	animation: animation1 var(--timer) ease 0s infinite normal none;
}
#preview {
	animation: animation1 var(--timer) ease 0s infinite normal none;
}
@keyframes animation1 {
	0%,50%,100% {
		opacity: 1;
	}
	25%,75% {
		opacity: 0;
	}
}
</style>
	<section>
		<!-- <form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
		  <input type="range" id="b" name="b" value="50"> +
		  <input type="number" id="a" name="a" value="10"> =
		  <output name="result" for="a b">60</output>
		</form> -->
		<form>
			<fieldset>
				<legend>Choose the frequency</legend>
				<label for="hertz-range">Hertz</label>
				<input type="range" id="hertz-range" value="50" min="0" max="100" step="1">
				<p>CSS code: <span class="code">animation-duration: <output id="hertz-range-output"></output>s;</span></p>
				<label for="output-seconds">Seconds</label>
				<output id="output-seconds">0</output>
			</fieldset>
		</form>
		<br>
		<p>For CSS we need seconds. Therefore we need to convert from Hertz to seconds first: <a href="https://www.unitjuggler.com/convert-frequency-from-Hz-to-s(p).html">Converter</a> or <a href="https://youtu.be/ytfOlvmxQUM">Explanation video</a></p>
	</section>
	<section>
		<div class="example-box-wrapper">
			<button>⏸️
				<span class="visually-hidden">Pause</span>
			</button>
			<div class="example-box" id="example-01">&nbsp;</div>
		</div>
		<!-- <div class="example-box-wrapper"> 
			<button>⏸️
				<span class="visually-hidden">Pause</span>
			</button>
			<div class="example-box" id="preview">
				&nbsp;
			</div>
		</div>-->
	</section>
    <script>
var hertzRange = document.getElementById('hertz-range');
var hertzRangeStartValue = document.getElementById('hertz-range').value;
var hertzRangeOutput = document.getElementById('hertz-range-output');
var example01 = document.getElementById('example-01');
hertzRangeOutput.value = hertzRangeStartValue;
hertzRange.oninput = function(event){
	hertzRangeOutput.innerHTML = hertzRange.value;
}
hertzRange.onchange = function(event){
	console.log(hertzRange.value);
	example01.style.setProperty('--timer', hertzRange.value +'s');
}
</script>
 </div>