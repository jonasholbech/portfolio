<script>
    function getColor() {
        return `hsl(${Math.floor(Math.random() * 360)}, 50%, 50%)`;
    }
    let animationDuration = 4;
    function getPairs(numPoints) {
        const xMin = 106;
        const xMax = 106 + 300;
        const yMin = 26;
        const yMax = 26 + 171;
        let lastX = getRandomInt(xMin, xMax);
        let lastY = getRandomInt(yMin, yMax);
        let points = [];
        for (let i = 0; i < numPoints; i++) {
            const changeOn = Math.random() > 0.5 ? "x" : "y";
            if (changeOn === "x") {
                lastX = getRandomInt(xMin, xMax);
            } else {
                lastY = getRandomInt(yMin, yMax);
            }
            points.push(`${lastX},${lastY}`);
        }
        return points.join(" ");
    }
    function getRandomInt(min, max) {
        return Math.floor(Math.random() * (max - min + 1)) + min;
    }
    let pathPoints = getPairs(10);
    function animationIterationComplete() {
        pathPoints = getPairs(Math.random() * 15);
    }
</script>

<style>
    .screen {
        fill: darkslategray;
    }
    .chair {
        fill: var(--chair);
    }
    .snake {
        stroke: yellow;
        stroke-width: 10px;
        fill: none;
        stroke-dasharray: 1;
        stroke-dashoffset: 1;
        animation: var(--gameSpeed) var(--delay) snake infinite linear;
    }
    @keyframes snake {
        to {
            stroke-dashoffset: 0;
        }
    }
</style>

<svg
    viewBox="0 0 512 512"
    style="--chair:{getColor()}; --delay: {Math.random() * 10 - 5}s; --gameSpeed: {animationDuration}s;">
    <rect class="screen" x="106" y="26" width="301" height="171" />

    <g id="snake">
        <polyline
            pathLength="1"
            class="snake"
            points={pathPoints}
            on:animationiteration={animationIterationComplete} />
    </g>

    <rect class="chair" x="168" y="172" width="174.5" height="174.5" />
    <g>
        <path
            d="M496,296v-32c0-4.4-3.6-8-8-8H384v-8c0-13.2-10.8-24-24-24h-8v-16h40c13.2,0,24-10.8,24-24V40c0-13.2-10.8-24-24-24H120
		c-13.2,0-24,10.8-24,24v144c0,13.2,10.8,24,24,24h40v16h-8c-13.2,0-24,10.8-24,24v8H24c-4.4,0-8,3.6-8,8v32c0,4.4,3.6,8,8,8h15
		L16.1,487c-0.3,2.3,0.4,4.5,1.9,6.2c1.5,1.7,3.7,2.7,6,2.7h16c3.6,0,6.7-2.3,7.7-5.8L102,304h26v24c0,4.4,3.6,8,8,8h24v16
		c0,4.4,3.6,8,8,8h64v48h-56c-4.4,0-8,3.6-8,8v33.4c-12.5,4.4-19,18.1-14.6,30.6c4.4,12.5,18.1,19,30.6,14.6
		c12.5-4.4,19-18.1,14.6-30.6c-2.4-6.8-7.8-12.2-14.6-14.6V424h64v25.4c-12.5,4.4-19,18.1-14.6,30.6c4.4,12.5,18.1,19,30.6,14.6
		c12.5-4.4,19-18.1,14.6-30.6c-2.4-6.8-7.8-12.2-14.6-14.6V424h64v25.4c-12.5,4.4-19,18.1-14.6,30.6c4.4,12.5,18.1,19,30.6,14.6
		c12.5-4.4,19-18.1,14.6-30.6c-2.4-6.8-7.8-12.2-14.6-14.6V416c0-4.4-3.6-8-8-8h-56v-48h64c4.4,0,8-3.6,8-8v-16h24c4.4,0,8-3.6,8-8
		v-24h26l54.3,186.2c1,3.4,4.1,5.8,7.7,5.8h16c2.3,0,4.5-1,6-2.7c1.5-1.7,2.2-4,1.9-6.2L473,304h15C492.4,304,496,300.4,496,296z
		 M34,480h-1l22-176h30.3L34,480z M128,288H32v-16h96V288z M160,320h-16v-72c0-4.4,3.6-8,8-8h8V320z M176,480c-4.4,0-8-3.6-8-8
		s3.6-8,8-8s8,3.6,8,8S180.4,480,176,480z M336,464c4.4,0,8,3.6,8,8s-3.6,8-8,8s-8-3.6-8-8S331.6,464,336,464z M256,480
		c-4.4,0-8-3.6-8-8s3.6-8,8-8s8,3.6,8,8S260.4,480,256,480z M264,408h-16v-48h16V408z M336,344H176V184c0-4.4,3.6-8,8-8h144
		c4.4,0,8,3.6,8,8V344z M208,160v-16c0-26.5,21.5-48,48-48s48,21.5,48,48v16H208z M328,160h-8v-16c0-35.3-28.7-64-64-64
		s-64,28.7-64,64v16h-8c-13.2,0-24,10.8-24,24v8h-40c-4.4,0-8-3.6-8-8V40c0-4.4,3.6-8,8-8h272c4.4,0,8,3.6,8,8v144c0,4.4-3.6,8-8,8
		h-40v-8C352,170.8,341.2,160,328,160z M368,320h-16v-80h8c4.4,0,8,3.6,8,8V320z M479,480h-1l-51.4-176H457L479,480z M480,288h-96
		v-16h96V288z" />
    </g>
    <g class="head">
        <rect x="200.6" y="112" width="110.4" height="48" />
        <rect x="220" y="96" width="74" height="32" />
    </g>
</svg>
