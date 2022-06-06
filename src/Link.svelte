<script>
    const suffix = ['the-great', 'the-wild', 'the-silly', 'the-amazing', 'front-end-dev', 'the-dev', 'full-stack-dev']
    let random = Math.floor(Math.random() * suffix.length)
    export let width = 0
    $: radius = width / 22
    $: tri = width / 16

</script>

<a href='mailto:tijano+{suffix[random]}@gmail.com'>
<svg>
    <path d="m {width / 700} {width / 15.75} a {tri} {tri} 0 0 0 {tri * 2} 0 a {tri} {tri} 0 0 0 {tri * -2} 0" id='tri' stroke='none' fill='none'></path>

    <path d="m {width / 90} {width / 17} a {radius} {radius} 0 0 0 {radius * 2} 0 a {radius} {radius} 0 0 0 {radius * -2} 0" id='link' stroke='none' fill='none'></path>

    <text>
        <textPath href='#link'>tijano@gmail.com</textPath>
    </text>
    
</svg>
</a>

<style>
    
    a:hover, a:focus {
        background-color: transparent;
    }
    svg {
        width: 11.75vw;
        height: 11.75vw;
        padding: 5px;
        border-radius: 50%;
        position: absolute;
        top: 7vw;
        left: 7vw;
    }

    text {
        font-size: 2.25vw;
        letter-spacing: .8vw;
        fill: #ee6c4d;
        stroke-dasharray: 533;
        stroke-dashoffset: 3vw;
    }
    svg:hover, svg:focus {
        background-color: #8cd3db;
        padding: 0;
        border: 5px dotted #ee6c4d;
    }
    svg:hover text {
        fill: #f4f1de
    }
    
    
</style>