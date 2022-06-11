<script lang="ts">
    export let height
    export let width

    let fullMoon = new Date('5/16/2022').valueOf()
    let today = new Date('6/5/2022').valueOf()
    let difference = (today - fullMoon) / 1000 / 60 / 60 / 24
    while (difference > 29.5) {
        difference -= 29
    }
    let percent = (difference / 14)
    $: x = width > height ? width / 6 : (width * 1.77) / 6
    $: y = width > height ? width / 3 : (width * 1.77) / 3
    $: r = width > height ? width / 7 : (width * 1.77) / 7
    $: moonX = (x + r + r) - (r * (percent * 2))
    </script>
<p>
{moonX.toFixed(3)} //: m\<span class='blue'>\\</span>\\
{percent} 
</p>
<svg>
    <circle cx={x} cy={y} r={r} class='moon'/>

    <circle cx={moonX} cy={y} r={r} class='shade' />
        
    <circle class='dots turn' cx={x + 4} cy={y - 7} r={r - 5} fill="transparent" stroke-dasharray='5 15' stroke-dashoffset='11' />
    <text x={x * .75} y={y * 1.5} class='day' >{new Date().getMonth() + 1}/</text>
    <text x={x * .75} y={y * 1.5} class='month'>{new Date().getDate()}</text>
</svg>


<style>
    svg {
        position: fixed;
        top: .5%;
        left: 2%;
        z-index: -100;
        height: 56vw;
        width: 100%;
        background-color: #1f5d5e;
    }
    .moon {
        fill: #f4f1de
    }
    .dots {
        stroke: #db7b65;
        stroke-width: 4;
    }
    .shade {
        fill: #8cd3db;
    }
    
    text {
        fill: #4cb3a0;
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
        color: #ee6c4d;
    }      
    .day {
        font-size: 11vw;
    }   
    .month {
        font-size: 55vw;

    } 
    @media (orientation: portrait) {
        svg {
            height: 97vw;

        }
    }
    @media (prefers-color-scheme: light) {
        svg {
            background-color: #f4f1de;
        }
        .blue {
            color: #8cd3db;
        }
        .shade {
            fill: #f4f1de
        }
        .moon {
            fill: #8cd3db
        }
        .dots {
        stroke: #000;
        stroke-width: 2;
    }
        text {
            fill: #f7ff58;
        }
    }
</style>