<script lang="ts">
    export let height
    export let width

    let fullMoon = new Date('5/16/2022').valueOf()
    let today = new Date('6/20/2022').valueOf()
    let difference = (today - fullMoon) / 1000 / 60 / 60 / 24
    while (difference > 29.5) {
        difference -= 29
    }
    let percent = (difference / 14)
    $: x = width / 6
    $: y = width / 3
    $: r = width / 7
    $: moonX = (x + r + r) - (r * (percent * 2))
    
        
    console.log(difference)
</script>
{moonX.toFixed(3)} //: \<span class='blue'>\\</span>\\
{percent}
<svg>
    <circle cx={x} cy={y} r={r} fill='#8cd3db' />

    <circle cx={moonX} cy={y} r={r}  fill='#f4f1de' />
        
    <circle cx={x + 4} cy={y - 7} r={r - 5} stroke="black" stroke-width="2" fill="transparent" stroke-dasharray='5 15' stroke-dashoffset='11' class='turn' />
    <text x={x * .5} y={y * 1.5} font-size={width / 20}>{new Date().getMonth() + 1}/</text>
    <text x={x * .75} y={y * 1.5} font-size={width * .55} >{new Date().getDate()}</text>
</svg>


<style>
    svg {
        position: fixed;
        top: .5%;
        left: 2%;
        z-index: -100;
        height: 56vw;
        width: 100%;
        background-color: #f4f1de;
    }
    text {
        fill: #f7ff58;
    }
    @keyframes dash {
        to {
            stroke-dashoffset: 0;
        }
    }
    .turn {
        stroke-dasharray: 5 15;
        stroke-dashoffset: 1000;
        animation: dash 1800s linear forwards;
    }
    .blue {
        color: #8cd3db;
    }
    @media (orientation: portrait) {
        svg {
            height: 100%;
            width: 100%;
        }       
    }
</style>