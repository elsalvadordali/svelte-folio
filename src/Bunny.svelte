

<div class="line bottom">
    <h4 class='title'><a href='https://bunnymoney.app/' target="_new">Bunny Money</a></h4>
    <h4>A Progressive Web App that teaches kids financial literacy, 
        created in svelte.js and typescript. Use firebase auth for authentication,
         and firestore for storage.</h4>
</div>


<style>
    .line {
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-evenly;
    }
    h4 {
        margin: 0;
        padding: 1vw;
        font-size: 1.5vw;
        font-family: monospace;
        font-weight: 100;
    }
    .title {
        border-right: 2px solid #e5e5e5;
        font-size: 4vw;
        padding: 2vw .5vw;
        font-family: 'Bebas Neue', cursive;
    }
    
    @media (orientation: portrait) {
        
        h4 {
            font-size: 1.5vh;
            padding: 1vh;
        }
        .title {
            font-size: 4vh;
            padding: 2vh .5vh;
        }
    }
    @media (prefers-color-scheme: light) {
        a:hover, a:focus {
            font-style: italic;
            background-color: #f7ff58;
        }
        .title {
            border-right: 2px solid #8cd3db;
        }
    }
</style>